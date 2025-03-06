---
title: incremetarePeInterval
date: 29-Oct-2024
description: 
tags: []
---

```c
Acest cod C afișează două linii de numere întregi. Prima linie conține numerele de la 1 la 10 în ordine crescătoare, iar a doua linie conține numerele de la 10 la 1 în ordine descrescătoare.

**Analiza codului:**

1.  **`#include <stdio.h>`:** Include header-ul standard de input/output pentru a utiliza funcția `printf()`.

2.  **`int main(void)`:** Funcția principală a programului.

3.  **`int i = 1;`:** Declară o variabilă întreagă `i` și o inițializează cu valoarea 1. Această variabilă va fi folosită ca contor în bucle.

4.  **`for (i; i <= 10; i++) { ... }`:** Această buclă `for` iterează de la 1 la 10 (inclusiv).
    *   `i;`: Inițializarea buclei este omisă, deoarece `i` a fost deja inițializată înainte de buclă.
    *   `i <= 10;`: Condiția de continuare a buclei. Bucla continuă să se execute atâta timp cât `i` este mai mic sau egal cu 10.
    *   `i++`: Incrementează valoarea lui `i` cu 1 după fiecare iterație.
    *   `printf("%3d", i);`: Afișează valoarea lui `i` cu o lățime de 3 caractere. Formatul `%3d` asigură că numerele sunt aliniate la dreapta, chiar dacă au mai puține de 3 cifre.

5.  **`printf("\n");`:** Afișează un caracter newline pentru a trece la linia următoare.

6.  **`for (i = 10; i >= 1; i--) { ... }`:** Această buclă `for` iterează de la 10 la 1 (inclusiv) în ordine descrescătoare.
    *   `i = 10;`: Inițializează valoarea lui `i` cu 10.
    *   `i >= 1;`: Condiția de continuare a buclei. Bucla continuă să se execute atâta timp cât `i` este mai mare sau egal cu 1.
    *   `i--`: Decrementează valoarea lui `i` cu 1 după fiecare iterație.
    *   `printf("%3d", i);`: Afișează valoarea lui `i` cu o lățime de 3 caractere.

7.  **`return 0;`:** Indică faptul că programul s-a executat cu succes.

**Ce face programul:**

Programul afișează două linii de numere întregi. Prima linie conține numerele de la 1 la 10 în ordine crescătoare, iar a doua linie conține numerele de la 10 la 1 în ordine descrescătoare.

**Ieșirea programului:**

```
  1  2  3  4  5  6  7  8  9 10
 10  9  8  7  6  5  4  3  2  1
```

```
