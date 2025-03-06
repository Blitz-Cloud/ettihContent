---
title: citireChar
date: 19-Nov-2024
description: 
tags: []
---

```c
#include <stdio.h>
#include <string.h>

int main(void) {
    char input[255];
    fgets(input, 255, stdin);
    strchr(input, "\n");
    return 0;
}

```
