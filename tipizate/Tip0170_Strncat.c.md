---
title: Strncat.c
date: Tip0170
description: 
tags: []
---

```c
#include <stdio.h>#include <string.h>

void main(void)
 {
   char name[64] = "Bill";

   strncat(name, " and Hillary", 4);
   printf("Did you vote for %s?\n", name);
 }

```
