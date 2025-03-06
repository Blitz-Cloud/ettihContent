---
title: nrDeConsoane
date: 5-Nov-2024
description: 
tags: []
---

```c
#include <stdio.h>
#include <string.h>

int main(void) {
    char a='a';
    int n=0;
    for(;a<='z';a++) {
        if(!strchr("aeiou",a)) {
            n++;
        }
    }
    printf("%d\n",n);
    return 0;
}

```
