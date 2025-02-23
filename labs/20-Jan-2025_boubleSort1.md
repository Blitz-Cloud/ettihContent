---
title: boubleSort1
date: 20-Jan-2025
description: 
tags: []
---

```c
#include <stdio.h>

void variantaMaiGrea(){
  int v[]={10,100,4,9,12,65,8,90,75,1};
    int i,j;
    for(i=0;i<9;i++){
        for(j=i;j<10;j++){
            if(v[i]>v[j]){
                int aux=v[i];
                v[i]=v[j];
                v[j]=aux;
            }
        }
        for(j=0;j<10;j++){
        printf("%d",v[j]);
    }
        printf(";\n");
    }
    for(i=0;i<10;i++){
        printf("%d",v[i]);
    }

}

void variantaUsoara(){

    int v[]={10,100,4,9,12,65,8,90,75,1};
    int i,j,ok=1;
    for(i=1;i<=9 && ok;i++){
        ok=0;
        for(j=1;j<=9;j++){
            if(v[j]>v[j+1]){
                int aux=v[j+1];
                v[j+1]=v[j];
                v[j]=aux;
                ok=1;
            }
        }
    }
    for(i=1;i<=9;i++){
        printf("%d ",v[i]);
    }
}

int main(void) {
    //variantaMaiGrea();
    variantaUsoara();
    return 0;
}

```
