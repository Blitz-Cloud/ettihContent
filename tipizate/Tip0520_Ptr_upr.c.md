---
title: Ptr_upr.c
date: Tip0520
description: 
tags: []
---

```c
#include <stdio.h>#include <ctype.h>

char *string_uppercase(char *string)
 {
   char *starting_address;

   starting_address = string;

   while (*string)
     toupper(*string++);

   return(starting_address);
 }

void main(void)
 {
   char *title = "Jamsa\'s C/C++ Programmmer\'s Bible";
   char *string;

   string = string_uppercase(title);
   printf("%s\n", string);

   printf("%s\n", string_uppercase("Arrays and Pointers"));
 }

```
