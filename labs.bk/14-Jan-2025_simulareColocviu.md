---
title: simulareColocviu
date: 14-Jan-2025
description: 
tags: []
---

```c
#include <stdio.h>


//definire gamer

struct gamer {
    char alias[9];
    char nume[9];
    int varsta;
    int scor;
} jucatori[4];
int pozAcctuala =0;

// afisare meniu
 void afisare() {
     printf("0-Listeaza toate aliasurile in ordinea introdusa\n");
     printf("1-Introducere jucatori\n");
     printf("2-Afiseaza scorul pt un alias dat");
     printf("3-Afisare clasament\n");
     printf("4-Lista aliasurilor cu varsta mai mare decat cea citita\n");
     printf("5-Iesire din program\n");
 }


//listare toti
void afisareJucatoriIntrodusi() {
     for(int i = 0; i < pozAcctuala; i++) {
        printf("%s %s %d %d\n", jucatori[i].nume, jucatori[i].alias,jucatori[i].varsta,jucatori[i].scor);
     }
 }


//citire gamer
void introducereJucator() {
     scanf("%s %s %d %d", &jucatori[pozAcctuala].alias, &jucatori[pozAcctuala].nume, &jucatori[pozAcctuala].varsta, &jucatori[pozAcctuala].scor);
     pozAcctuala++;
 }

//afisare jucator dupa alias
void afisareJucatorDupaAlias(char alias[]) {
     for(int i = 0; i < pozAcctuala; i++) {
         if(jucatori[i].alias == alias) {
             printf("%s %s %d %d\n", jucatori[i].nume, jucatori[i].alias,jucatori[i].varsta,jucatori[i].scor);
             break;
         }
     }
 }



int main(void) {
         int comanda;
         while (1) {
             afisare();
             scanf("%d", &comanda);
             switch (comanda) {
                 case 0:
                     afisareJucatoriIntrodusi();
                 break;
                 case 1:
                     introducereJucator();
                 break;
                 case 2:
                     char alias[9];
                    scanf("%s", &alias);
                    afisareJucatorDupaAlias(alias);
                 break;
                 case 3:

                     break;
                 case 4:break;
                 case 5:
                     return 0;
                 default:break;
             }
         }
         return 0;
     }


```
