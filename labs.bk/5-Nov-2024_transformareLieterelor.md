---
title: transformareLieterelor
date: 5-Nov-2024
description: 
tags: []
---

```c
Acest cod C citește un caracter de la intrare și apoi intră într-o buclă care transformă caracterul în majusculă dacă este o literă mică, sau în minusculă dacă nu este o literă mică. Apoi, afișează caracterul original și caracterul transformat. Utilizatorul poate continua transformările introducând 'D' sau 'd', sau poate ieși din program introducând 'N' sau 'n'.

**Analiza codului:**

1.  **`#include <ctype.h>`:** Include header-ul `ctype.h` pentru a utiliza funcțiile `toupper()` și `tolower()`.

2.  **`#include <stdio.h>`:** Include header-ul `stdio.h` pentru a utiliza funcțiile `printf()` și `getchar()`.

3.  **`int main(void)`:** Funcția principală a programului.

4.  **`char c, copy, cmd = 'd';`:** Declară trei variabile de tip `char`:
    *   `c`: Va stoca caracterul citit de la intrare.
    *   `copy`: Va stoca copia transformată a caracterului.
    *   `cmd`: Va stoca comanda introdusă de utilizator ('D' sau 'N'). Este inițializată cu 'd' pentru a intra în buclă.

5.  **`c = getchar();`:** Citește un caracter de la intrare standard (tastatură) și îl stochează în variabila `c`.

6.  **`getchar();`:** Citește un caracter de la intrare standard și îl ignoră. Aceasta este folosit pentru a consuma caracterul newline (`\n`) care este lăsat în buffer-ul de intrare după ce utilizatorul apasă Enter.

7.  **`while (cmd == 'd') { ... }`:** Această buclă `while` continuă să se execute atâta timp cât valoarea variabilei `cmd` este 'd'.

8.  **`copy = 'a' <= c && c <= 'z' ? toupper(c) : tolower(c);`:** Aceasta este o expresie condițională (operatorul ternar).
    *   `'a' <= c && c <= 'z'`: Verifică dacă `c` este o literă mică.
    *   `toupper(c)`: Dacă `c` este o literă mică, transformă-l în majusculă folosind funcția `toupper()` din `ctype.h`.
    *   `tolower(c)`: Dacă `c` nu este o literă mică, transformă-l în minusculă folosind funcția `tolower()` din `ctype.h`.
    *   Rezultatul transformării este stocat în variabila `copy`.

9.  **`printf("litera %c a devenit %c\n", c, copy);`:** Afișează caracterul original (`c`) și caracterul transformat (`copy`).

10. **`copy = c;`:** Atribuie valoarea lui `c` variabilei `copy`. Această linie nu are niciun efect vizibil, deoarece `copy` este suprascrisă la fiecare iterație a buclei.

11. **`printf("D continua transformarile N iese din program\n");`:** Afișează un mesaj care solicită utilizatorului să introducă o comandă.

12. **`cmd = getchar();`:** Citește un caracter de la intrare standard și îl stochează în variabila `cmd`.

13. **`cmd = tolower(cmd);`:** Transformă caracterul introdus în minusculă folosind funcția `tolower()`.

14. **`getchar();`:** Citește un caracter de la intrare standard și îl ignoră. Aceasta este folosit pentru a consuma caracterul newline (`\n`) care este lăsat în buffer-ul de intrare după ce utilizatorul apasă Enter.

15. **`return 0;`:** Indică faptul că programul s-a executat cu succes.

**Ce face programul:**

Programul citește un caracter de la intrare și apoi intră într-o buclă. În interiorul buclei, transformă caracterul în majusculă dacă este o literă mică, sau în minusculă dacă nu este o literă mică. Apoi, afișează caracterul original și caracterul transformat. Utilizatorul poate continua transformările introducând 'D' sau 'd', sau poate ieși din program introducând 'N' sau 'n'.

**Exemplu de execuție:**

```
a
litera a a devenit A
D continua transformarile N iese din program
d
litera a a devenit A
D continua transformarile N iese din program
N
```

```
