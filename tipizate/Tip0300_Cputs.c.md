---
title: Cputs.c
date: Tip0300
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
   for (count = 0; count < 1500; count++)
     puts("Jamsa\'s C/C++ Programmer\'s Bible");
   time(&stop_time);

   printf("\n\nTime required for puts %d seconds\n",
     stop_time-start_time);
   printf("Press any key...\n");
   getch();

   time(&start_time);
   for (count = 0; count < 1500; count++)
     cputs("Jamsa\'s C/C++ Programmer\'s Bible\r\n");
   
   time(&stop_time);

   printf("\n\nTime required for cputs %d seconds\n", 
     stop_time-start_time);
 }


```
