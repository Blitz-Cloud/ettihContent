---
title: Odd_even.c
date: Tip0126
description: 
tags: []
---

```c
#include <stdio.h>
void main(void)
 {
   int counter;

   printf("\nEven values\n");
   for (counter = 1; counter <= 100; counter++)
     {
       if (counter % 2)  // Odd
         continue;

       printf("%d ", counter);
     }

   printf("\nOdd values\n");
   counter = 0;
   while (counter <= 100) 
     {
       counter++;

       if (! (counter % 2)) // Even 
         continue;

       printf("%d ", counter);
     }
 }


```
