---
title: citirede10Char
date: 19-Nov-2024
description: 
tags: []
---

```c
Acest cod C citește trei caractere de la intrare, le stochează într-un array și apoi le afișează în ordine inversă.

**Analiza codului:**

1.  **`#include <stdio.h>`:** Include header-ul standard de input/output pentru a utiliza funcțiile `printf()` și `getchar()`.

2.  **`int main(void)`:** Funcția principală a programului.

3.  **`char a[11], in;`:** Declară:
    *   `a[11]`: Un array de caractere numit `a` cu 11 elemente.  Acesta va fi folosit pentru a stoca caracterele citite.  Dimensiunea 11 este aleasă pentru a permite stocarea a maximum 10 caractere + terminatorul null (`\0`).
    *   `in`: O variabilă de tip `char` numită `in`.  Aceasta va fi folosită pentru a stoca temporar fiecare caracter citit de la intrare.

4.  **`int i;`:** Declară o variabilă întreagă `i` pentru a fi folosită ca index în bucle.

5.  **`for (i = 0; i < 3; i++) { ... }`:** Această buclă `for` iterează de trei ori.

6.  **`in = getchar();`:** Citește un caracter de la intrare standard (tastatură) și îl stochează în variabila `in`.

7.  **`getchar();`:** Citește un caracter de la intrare standard și îl ignoră.  Acest lucru este folosit pentru a consuma caracterul newline (`\n`) care este lăsat în buffer-ul de intrare după ce utilizatorul apasă Enter.

8.  **`a[i] = in;`:** Stochează caracterul citit în variabila `in` în array-ul `a` la indexul `i`.

9.  **`a[i] = '\0';`:** După ce bucla `for` se termină, această linie adaugă terminatorul null (`\0`) la sfârșitul șirului de caractere din array-ul `a`.  Acest lucru este important pentru a marca sfârșitul șirului, astfel încât funcțiile care lucrează cu șiruri de caractere (cum ar fi `printf("%s", a)`) să știe unde se termină șirul.

10. **`for (i = 2; i >= 0; i--) { ... }`:** Această buclă `for` iterează prin array-ul `a` în ordine inversă (de la indexul 2 la indexul 0).

11. **`printf("%c", a[i]);`:** Afișează caracterul de la indexul `i` al array-ului `a`.

12. **`return 0;`:** Indică faptul că programul s-a executat cu succes.

**Ce face programul:**

Programul citește trei caractere de la utilizator, câte unul pe linie (apăsând Enter după fiecare caracter). Apoi, afișează aceste caractere în ordine inversă.

**Exemplu de execuție:**

Dacă utilizatorul introduce următoarele caractere:

```
a
b
c
```

Programul va afișa:

```
cba
```

**Explicație:**

*   Programul citește caracterul 'a' și îl stochează în `a[0]`.
*   Programul citește caracterul newline (`\n`) și îl ignoră.
*   Programul citește caracterul 'b' și îl stochează în `a[1]`.
*   Programul citește caracterul newline (`\n`) și îl ignoră.
*   Programul citește caracterul 'c' și îl stochează în `a[2]`.
*   Programul citește caracterul newline (`\n`) și îl ignoră.
*   Programul adaugă terminatorul null la `a[3]`.
*   Programul afișează caracterele `a[2]`, `a[1]` și `a[0]` în ordine inversă, rezultând șirul "cba".

```
