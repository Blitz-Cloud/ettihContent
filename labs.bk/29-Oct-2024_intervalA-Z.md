---
title: intervalA-Z
date: 29-Oct-2024
description: 
tags: []
---

```c
#include <stdio.h>

int main(void) {
    char i,j=0;
    for (i='a';i<='z';i++) {
        if (j==20) {
            printf("\n");
        }
        j++;
        printf("%3c ",i);
    }
    return 0;
}

```
