---
title: For_down.c
date: Tip0116
description: 
tags: []
---

```c
#include <stdio.h>
void main(void)
 {
   int counter;

   for (counter = 5; counter >= 1; counter--)
    printf("%d ", counter);

   printf("\nStarting second loop\n");
   
   for (counter = 10; counter >= 1; counter--)
    printf("%d ", counter);

   printf("\nStarting third loop\n");

   for (counter = 0; counter >= 1; counter--)
    printf("%d ", counter);
 }

```
