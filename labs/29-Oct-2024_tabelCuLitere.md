---
title: tabelCuLitere
date: 29-Oct-2024
description: 
tags: []
---

```c
#include <stdio.h>

void linieTabel() {
    int i,j;
    for(i=0;i<4;i++) {
        printf("|");
        for(j=0;j<5;j++) {
            printf("-");
        }
    }
    printf("|\n");
}
void casuta(char format[], char c ) {
    printf(format,c);
    printf("|");
}

void main() {
    int i,j;
    linieTabel();
    printf("|liter|cod10|cod 8|cod16|\n");
    for(i=0;i<4;i++) {
        linieTabel();
        char c = 'a'+i;
        printf("|");
        casuta("%5c",c);
        casuta("%#5d",c);
        casuta("%#5o",c);
        casuta("%#5x",c);
        printf("\n");
    }
    linieTabel();}
```
