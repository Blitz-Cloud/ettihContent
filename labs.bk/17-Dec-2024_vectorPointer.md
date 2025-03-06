---
title: vectorPointer
date: 17-Dec-2024
description: 
tags: []
---

```c
Acest cod C definește o structură de tip `union` numită `A` care conține două variabile membre de tip `int`: `val` și `val1`. Apoi, citește o valoare întreagă de la utilizator și o stochează în variabila `val` a uniunii. În final, afișează valoarea stocată în `val` în format octal.

**Analiza codului:**

1.  **`#include <stdio.h>`:** Include header-ul standard de input/output pentru a utiliza funcțiile `printf()` și `scanf()`.

2.  **`union A { ... };`:** Definește o uniune numită `A`.
    *   `int val, val1;`: Declară două variabile membre de tip `int` numite `val` și `val1`.

3.  **`int main(void)`:** Funcția principală a programului.

4.  **`union A nr;`:** Declară o variabilă `nr` de tip `union A`.

5.  **`scanf("%d", &nr.val);`:** Citește o valoare întreagă de la intrare standard (tastatură) și o stochează în variabila `val` a uniunii `nr`.

6.  **`printf("%o\n", nr.val);`:** Afișează valoarea stocată în variabila `val` a uniunii `nr` în format octal.
    *   `%o`: Specificatorul de format `%o` în `printf()` este folosit pentru a afișa un număr întreg în format octal (baza 8).

7.  **`return 0;`:** Indică faptul că programul s-a executat cu succes.

**Ce face programul:**

Programul solicită utilizatorului să introducă un număr întreg. Apoi, afișează același număr în format octal.

**Exemplu de execuție:**

Dacă utilizatorul introduce valoarea `10`, programul va afișa:

```
12
```

**Explicație:**

*   O uniune este o structură de date specială care permite stocarea diferitelor tipuri de date în aceeași locație de memorie.
*   În acest caz, uniunea `A` poate stoca fie un număr întreg în variabila `val`, fie un număr întreg în variabila `val1`.  Însă, `val` și `val1` partajează aceeași locație de memorie.  Modificarea uneia dintre ele va afecta și valoarea celeilalte.
*   Programul citește un număr întreg și îl stochează în `nr.val`.  Apoi, afișează valoarea lui `nr.val` în format octal.  Numărul 10 în baza 10 este echivalent cu 12 în baza 8.

```
