---
title: Show_oh.c
date: Tip0067
description: 
tags: []
---

```c
#include <stdio.h>
void main(void)
 {
   int value = 255;

   printf("The decimal value %d in octal is %#o\n", value, value);
   printf("The decimal value %d in hexadecimal is %#x\n", value, value);
   printf("The decimal value %d in hexadecimal is %#X\n", value, value);
 }


```
