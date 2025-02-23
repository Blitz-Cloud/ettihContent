---
title: Str_ptr.c
date: Tip0518
description: 
tags: []
---

```c
#include <stdio.h>
void show_string(char *string)
 { 
   while (*string)
     putchar(*string++);
 }

void main(void)
 {
   show_string("Jamsa\'s C/C++ Programmer\'s Bible");
 }


```
