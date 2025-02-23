---
title: cursPcl
date: 27-Nov-2024
description: 
tags: []
---

```c

#include <stdio.h>

int main(void) {
    int a=9,b=10;
    printf("a=%p,b=%p\n",&a,&b);
    printf("dif=%p",&b-&a);
    int *pa;
    pa=&a;
    (double *)pa;
    printf("%d",*pa);

    return 0;
}

```
