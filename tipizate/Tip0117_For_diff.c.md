---
title: For_diff.c
date: Tip0117
description: 
tags: []
---

```c
#include <stdio.h>
void main(void)
 {
   int counter;

   for (counter = -100; counter <= 100; counter += 5)
    printf("%d ", counter);

   printf("\nStarting second loop\n");
   
   for (counter = 100; counter >= -100; counter -= 25)
    printf("%d ", counter);
 }

```
