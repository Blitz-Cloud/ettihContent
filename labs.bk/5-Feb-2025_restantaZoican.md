---
title: restantaZoican
date: 5-Feb-2025
description: 
tags: []
---

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX 256

// Functia pentru inserarea zgomotului uniform (0-10)
char insert_noise(char *pixel, int x, int y, int width, int height) {
    int noise = (x + y) % 11; // Zgomot simplu bazat pe coordonate
    int newValue = *pixel + noise;
    if (newValue > 255) newValue = 255; // Asiguram ca valoarea nu depaseste 255
    return (char)newValue;
}

// Functia pentru eliminarea zgomotului prin mediere aritmetica
char remove_noise(char *image, int x, int y, int width, int height) {
    int sum = 0, count = 0;
    for (int i = -1; i <= 1; ++i) {
        for (int j = -1; j <= 1; ++j) {
            sum += image[(x + i) * (width + 2) + (y + j)]; // Include bordura de 0-uri
            count++;
        }
    }
    return (char)(sum / count);
}

// Functia de prelucrare a imaginii
// prelucrare_img accepta ca parametrii 2 pointeri catre fisiere si o functie de care
// da return la un char si are antetul (char *,int,int,int,int), adica primeste ca parametrii
// pointer catre un char, si 4 numere
void prelucrare_img(FILE *imgO, FILE *imgP, char (*funcptr)(char *, int, int, int, int)) {
    int width, height;
    fread(&width, sizeof(int), 1, imgO);
    fread(&height, sizeof(int), 1, imgO);

    // Alocare dinamica pentru matricea extinsa cu bordura de 0-uri
    char *image = (char *)calloc((width + 2) * (height + 2), sizeof(char)); // +2 pentru bordura

    // Citirea imaginii originale in matricea extinsa
    for (int x = 1; x <= height; ++x) {
        fread(image + x * (width + 2) + 1, sizeof(char), width, imgO);
    }

    // Procesare imagine pixel cu pixel, ignorand bordura
    for (int x = 1; x <= height; ++x) {
        for (int y = 1; y <= width; ++y) {
            image[x * (width + 2) + y] = funcptr(image, x, y, width, height);
        }
    }

    // se scrie dimensiunea imaginii in iesire sub forma (width,height)=(widthheight)
    fwrite(&width, sizeof(int), 1, imgP);
    fwrite(&height, sizeof(int), 1, imgP);

    // Scriem imaginea procesata in fisierul de iesire
    for (int x = 1; x <= height; ++x) {
        // este necesar inmultirea x*(width+2)+1 deoarece nu este o matrice bidimensionala
        fwrite(image + x * (width + 2) + 1, sizeof(char), width, imgP);
    }

    // Eliberare memorie
    free(image);
}

int sesiune() {
    char fileOpenName[100], fileSaveName[100];
    printf("Introdu numele fisierului de deschidere: ");
    scanf("%s", fileOpenName);

    printf("Introdu numele fisierului de salvare: ");
    scanf("%s", fileSaveName);

    // Deschidere fisiere
    FILE *imgO = fopen(fileOpenName, "rb");
    if (imgO == NULL) {
        perror("Eroare la deschiderea fisierului original");
        exit(EXIT_FAILURE);
    }

    FILE *imgP = fopen(fileSaveName, "wb");
    if (imgP == NULL) {
        perror("Eroare la deschiderea fisierului prelucrat");
        fclose(imgO);
        exit(EXIT_FAILURE);
    }

    // Aplicare zgomot
    prelucrare_img(imgO, imgP, insert_noise);
    fclose(imgO);
    fclose(imgP);

    // Re-deschidem imaginea cu zgomot si aplicam eliminarea zgomotului
    imgO = fopen(fileSaveName, "rb");
    imgP = fopen("final_image.bin", "wb");
    if (imgO == NULL || imgP == NULL) {
        perror("Eroare la redeschidere fisier");
        exit(EXIT_FAILURE);
    }
    prelucrare_img(imgO, imgP, remove_noise);

    // Inchidem fisierele
    fclose(imgO);
    fclose(imgP);

 return 0;
}

int creareVisier(){
    FILE *file = fopen("input", "wb");
    if (!file) {
        perror("Eroare la crearea fisierului");
        return 1;
    }

    int width = 5, height = 5; // A simple 5x5 grayscale image
    fwrite(&width, sizeof(int), 1, file);
    fwrite(&height, sizeof(int), 1, file);

    // Creating a simple image: all pixels have value 100
    char pixelValue = 100;
    for (int i = 0; i < width * height; i++) {
        fwrite(&pixelValue, sizeof(char), 1, file);
    }

    fclose(file);
    printf("Fisierul input.bin a fost creat cu succes!\n");
    return 0;
}

int printImage(char name[]){
    FILE *fin = fopen(name,"rb");
    if (fin == NULL) {
        perror("Eroare la deschiderea fisierului");
        return 1;
    }
    int width, height;
    fread(&width, sizeof(int),1,fin);
    fread(&height, sizeof(int),1,fin);
    for(int i=0;i<=width;i++) {
        for(int j=0;j<=height;j++){

        }
    }
    return 0;
}


int main(){
    // unsafe(!GPT!)
    // creareVisier();
    sesiune();
    return 0;
}
```
