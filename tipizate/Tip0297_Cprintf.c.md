---
title: Cprintf.c
date: Tip0297
description: 
tags: []
---

```c
#include <stdio.h>#include <conio.h>
#include <time.h>

void main(void)
 {
   int count;

   time_t start_time, stop_time;
   
   time(&start_time);
   for (count = 0; count < 1001; count++)
     printf("Jamsa\'s C/C++ Programmer\'s Bible\n");
   time(&stop_time);

   printf("\n\nTime required for printf %d seconds\n",
     stop_time-start_time);
   printf("Press any key...\n");
   getch();

   time(&start_time);
   for (count = 0; count < 1001; count++)
     cprintf("Jamsa\'s C/C++ Programmer\'s Bible\r\n");

   time(&stop_time);

   printf("\n\nTime required for cprintf %d seconds\n",
     stop_time-start_time);
 }


```
