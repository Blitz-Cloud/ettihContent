---
title: pointeriCu3Variabile
date: 17-Dec-2024
description: 
tags: []
---

```c
#include <stdio.h>

void swap(int* a, int* b) {
    int temp = *a;
    *a=*b;
    *b=temp;
}

int main(void) {
    int a=1,b=2,c=3;
    printf("a=%p b=%p c=%p\n",&a,&b,&c);
    swap(&a,&b);
    swap(&b,&c);
    printf("a=%d b=%d c=%d\n",a,b,c);
    return 0;
}

```
