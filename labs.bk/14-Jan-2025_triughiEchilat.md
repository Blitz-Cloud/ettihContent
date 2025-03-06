---
title: triughiEchilat
date: 14-Jan-2025
description: 
tags: []
---

```c
Acest cod C definește un array de 10 numere întregi, afișează elementele array-ului, adaugă 10 la fiecare element și apoi afișează din nou elementele array-ului.

**Analiza codului:**

1.  **`#include <stdio.h>`:** Include header-ul standard de input/output pentru a utiliza funcția `printf()`.

2.  **`int main(void)`:** Funcția principală a programului.

3.  **`int a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};`:** Declară un array de 10 numere întregi numit `a` și îl inițializează cu valorile 1, 2, 3, 4, 5, 6, 7, 8, 9 și 10.

4.  **`for (int i = 0; i < 10; i++) { ... }`:** Această buclă `for` iterează prin fiecare element al array-ului `a`.

5.  **`printf("%d ", *(a + i));`:** Afișează valoarea elementului curent al array-ului.
    *   `a + i`: Calculează adresa elementului de la indexul `i` al array-ului `a`.
    *   `*(a + i)`: Dereferențiază adresa calculată, obținând valoarea elementului de la indexul `i`.  Aceasta este echivalentă cu `a[i]`.

6.  **`for (int i = 0; i < 10; i++) { ... }`:** Această a doua buclă `for` iterează din nou prin fiecare element al array-ului `a`.

7.  **`*(a + i) = *(a + i) + 10;`:** Adaugă 10 la valoarea elementului curent al array-ului.
    *   `*(a + i)`: Dereferențiază adresa elementului de la indexul `i`, obținând valoarea curentă.
    *   `*(a + i) + 10`: Adaugă 10 la valoarea curentă.
    *   `*(a + i) = ...`: Atribuie noua valoare (valoarea curentă + 10) elementului de la indexul `i`.

8.  **`printf("\n");`:** Afișează un caracter newline pentru a trece la linia următoare.

9.  **`for (int i = 0; i < 10; i++) { ... }`:** Această a treia buclă `for` iterează din nou prin fiecare element al array-ului `a`.

10. **`printf("%d ", *(a + i));`:** Afișează valoarea elementului curent al array-ului (după ce a fost adăugat 10).

11. **`return 0;`:** Indică faptul că programul s-a executat cu succes.

**Ce face programul:**

Programul inițializează un array cu valorile de la 1 la 10. Apoi, afișează aceste valori. Apoi, adaugă 10 la fiecare valoare din array. În final, afișează din nou valorile array-ului, care vor fi acum de la 11 la 20.

**Ieșirea programului:**

```
1 2 3 4 5 6 7 8 9 10
11 12 13 14 15 16 17 18 19 20
```

```
