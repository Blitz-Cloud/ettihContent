---
title: vectorPointer
date: 17-Dec-2024
description: 
tags: []
---

```c

#include <stdio.h>

int main(void) {
    int a[10]={1,2,3,4,5,6,7,8,9,10};
    for(int i=0;i<10;i++) {
        printf("%d ",*(a+i));
    }
    for(int i=0;i<10;i++) {
        *(a+i)=*(a+i)+10;
    }
    printf("\n");
    for(int i=0;i<10;i++) {
        printf("%d ",*(a+i));
    }
    return 0;
}

```
