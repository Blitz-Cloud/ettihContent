---
title: interval
date: 12-Nov-2024
description: 
tags: []
---

```c
Acest cod C calculează și afișează valorile sinus pentru o serie de unghiuri exprimate în grade.

**Analiza codului:**

1.  **`#include <stdio.h>`:** Include header-ul standard de input/output pentru a utiliza funcția `printf()`.

2.  **`#include <math.h>`:** Include header-ul matematic pentru a utiliza funcția `sin()` și constanta `M_PI`.

3.  **`int main(void)`:** Funcția principală a programului.

4.  **`int i;`:** Declară o variabilă întreagă `i` pentru a fi folosită ca contor în buclă.

5.  **`float x[5]={0.0,30.0,45.0,60.0,90.0};`:** Declară un array de tip `float` numit `x` cu 5 elemente și îl inițializează cu valorile 0.0, 30.0, 45.0, 60.0 și 90.0. Aceste valori reprezintă unghiuri în grade.

6.  **`printf("%3c",'|');`**: Afișează un caracter '|' cu o lățime de 3 caractere.

7.  **`printf("%4c",' ');`**: Afișează un spațiu cu o lățime de 4 caractere.

8.  **`printf("%3c",'|');`**: Afișează un caracter '|' cu o lățime de 3 caractere.

9.  **`for(i=0;i<5;i++) { ... }`**: Această buclă `for` iterează prin fiecare element al array-ului `x`.
    *   `printf("%4d ",x[i]);`: Afișează valoarea lui `x[i]` (unghiul în grade) ca un număr întreg cu o lățime de 4 caractere, urmat de un spațiu.  Deși `x[i]` este `float`, este afișat ca `int`, deci partea fracționară este trunchiată.
    *   `printf("%3c",'|');`: Afișează un caracter '|' cu o lățime de 3 caractere.

10. **`for(i=0;i<5;i++) { ... }`**: Această buclă `for` iterează din nou prin fiecare element al array-ului `x`.
    *   `printf("%4.3f ", sin(x[i]*M_PI/180.0));`: Calculează sinusul unghiului `x[i]` (care este în grade) și îl afișează ca un număr `float` cu o lățime de 4 caractere și 3 zecimale, urmat de un spațiu.
        *   `x[i]*M_PI/180.0`: Convertăște unghiul din grade în radiani. `M_PI` este o constantă definită în `math.h` care reprezintă valoarea lui π (pi).
        *   `sin(...)`: Calculează sinusul unghiului în radiani.
    *   `printf("%3c",'|');`: Afișează un caracter '|' cu o lățime de 3 caractere.

11. **`return 0;`**: Indică faptul că programul s-a executat cu succes.

**Ce face programul:**

Programul afișează un tabel cu două rânduri. Primul rând conține unghiurile 0, 30, 45, 60 și 90 (exprimate în grade). Al doilea rând conține valorile sinus ale acestor unghiuri.  Formatarea cu `printf` este folosită pentru a alinia valorile în coloane.

**Ieșirea programului:**

```
|     |   |   0 |  30 |  45 |  60 |  90 |
0.000 |  30.000 |  45.000 |  60.000 |  90.000 |
```

(Notă: Ieșirea exactă poate varia ușor în funcție de implementarea funcției `printf` și de setările regionale.)
```
|     |   |   0 |  30 |  45 |  60 |  90 |
|0.000 |  30.000 |  45.000 |  60.000 |  90.000 |
```

```
|     |   |   0 |  30 |  45 |  60 |  90 |
|   |0.000 |  0.500 |  0.707 |  0.866 |  1.000 |
```

```
|     |   |   0 |  30 |  45 |  60 |  90 |
|   |0.000 |   |  0.500 |   |  0.707 |   |  0.866 |   |  1.000 |   |
```

```
