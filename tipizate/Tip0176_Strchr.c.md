---
title: Strchr.c
date: Tip0176
description: 
tags: []
---

```c
#include <stdio.h>#include <string.h>

void main(void)
 {
   char title[64] = "Jamsa\'s C/C++ Programmer\'s Bible!";
   char *ptr;

   ptr = strchr(title, 'C');
     if (*ptr)
     printf("First occurrence of C is at offset %d\n",
       ptr - title);
   else
     printf("Character not found\n");
 }

```
