---
title: Puttext.c
date: Tip0311
description: 
tags: []
---

```c
#include <conio.h>#include <io.h>
#include <fcntl.h>
#include <sys\stat.h>
#include <stdlib.h>
#include <dos.h>

void main(void)
 {
   char buffer[128];
   int row, column;    
   
   clrscr();
   cprintf("Jamsa\'s C/C++ Programmer\'s Bible\r\n");
   gettext(1, 1, 23, 1, buffer);

   while (! kbhit())
    {
      clrscr();
      row = 1 + random(24);
      column = 1 + random(58);
      puttext(column, row, column+22, row, buffer);
      delay(2000);
    }
 }


```
