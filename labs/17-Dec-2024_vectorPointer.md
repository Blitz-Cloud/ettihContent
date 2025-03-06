---
title: vectorPointer
date: 17-Dec-2024
description: 
tags: []
---

```c

#include <stdio.h>

int main(void) {
    int a[10]={1,2,3,4,5,6,7,8,9,10};
    for(int i=0;i<10;i++) {
        printf("%d ",*(a+i));
    }
    for(int i=0;i<10;i++) {
        *(a+i)=*(a+i)+10;
    }
    printf("\n");
    for(int i=0;i<10;i++) {
        printf("%d ",*(a+i));
    }
    return 0;
}

```

Acest cod C citește trei caractere de la intrare, le stochează într-un tablou și apoi le afișează în ordine inversă. Iată o explicație detaliată:

**1. Include-uri:**

*   `#include <stdio.h>`: Include fișierul antet standard pentru intrare/ieșire, necesar pentru funcțiile `printf` și `getchar`.

**2. Funcția `main()`:**

*   `int main(void)`: Definește funcția principală a programului, care nu primește argumente.
*   `char a[11],in;`: Declară două variabile:
    *   `char a[11]`: Un tablou de caractere numit `a` cu 11 elemente. Acesta va fi folosit pentru a stoca caracterele citite de la intrare. Dimensiunea 11 permite stocarea a 10 caractere plus terminatorul null (`\0`).
    *   `char in`: O variabilă de tip `char` numită `in`. Aceasta va fi folosită pentru a stoca temporar fiecare caracter citit de la intrare.
*   `int i;`: Declară o variabilă întreagă `i` pentru a fi folosită ca contor în buclă.
*   `for(i=0;i<3;i++) { ... }`: Inițializează o buclă `for` care iterează de la `i = 0` până la `i = 2` (inclusiv).
    *   `in = getchar();`: Citește un caracter de la intrare și îl stochează în variabila `in`.
    *   `getchar();`: Citește un caracter de la intrare și îl ignoră. Această linie este probabil destinată să consume caracterul newline (`\n`) care este introdus după fiecare caracter, dar nu este o abordare robustă.
    *   `a[i]=in;`: Stochează caracterul citit în variabila `in` în elementul `i` al tabloului `a`.
*   `a[i]='\0';`: Adaugă terminatorul null (`\0`) la sfârșitul șirului de caractere din tablou. Aceasta este important pentru a marca sfârșitul șirului, astfel încât funcțiile care lucrează cu șiruri de caractere (cum ar fi `printf` cu specificatorul `%s`) să știe unde se termină șirul.  În acest caz, `i` are valoarea 3 după terminarea buclei, deci terminatorul null este adăugat la `a[3]`.
*   `for(i=2;i>=0;i--) { printf("%c",a[i]); }`: Această buclă `for` iterează prin elementele tabloului `a` în ordine inversă (de la `i = 2` până la `i = 0`) și afișează fiecare caracter.
    *   `printf("%c",a[i]);`: Afișează caracterul stocat în elementul `i` al tabloului `a`.
*   `return 0;`: Returnează 0 pentru a indica faptul că programul s-a executat cu succes.

**Ce face programul:**

1.  Citește trei caractere de la intrare, câte unul pe linie (datorită `getchar()` suplimentar).
2.  Stochează aceste caractere într-un tablou.
3.  Afișează caracterele în ordine inversă.

**Exemplu de execuție:**

```
a
b
c
cba
```

În acest exemplu, utilizatorul a introdus caracterele 'a', 'b' și 'c', fiecare pe o linie separată. Programul a afișat apoi caracterele în ordine inversă: 'cba'.

**Probleme și îmbunătățiri:**

*   **Gestionarea caracterului newline:** Utilizarea `getchar()` pentru a consuma caracterul newline nu este o abordare robustă. Dacă utilizatorul introduce mai multe caractere pe o linie, `getchar()` va consuma doar primul caracter, iar restul vor rămâne în bufferul de intrare, ceea ce poate duce la comportament neașteptat. O abordare mai bună ar fi să se folosească `fgets` pentru a citi întreaga linie și apoi să se extragă caracterele dorite.
*   **Dimensiunea tabloului:** Tabloul `a` are o dimensiune de 11, dar programul citește doar 3 caractere. Ar fi mai bine să se declare tabloul cu o dimensiune mai mică (e.g., 4) pentru a economisi memorie.
*   **Lipsa validării intrării:** Programul nu validează intrarea utilizatorului. Dacă utilizatorul introduce mai puțin de 3 caractere, programul va avea un comportament imprevizibil. Ar trebui adăugată o validare a intrării pentru a asigura că programul funcționează corect.

**Exemplu de cod îmbunătățit:**

```c
#include <stdio.h>
#include <string.h>

int main(void) {
    char a[4];
    int i;

    printf("Introduceti 3 caractere, fiecare pe o linie:\n");
    for (i = 0; i < 3; i++) {
        if (fgets(a + i, 2, stdin) == NULL) {
            perror("Eroare la citirea caracterului");
            return 1;
        }
        a[i] = a[i][0]; // Extrage primul caracter din linia citita
    }
    a[i] = '\0';

    printf("Caracterele in ordine inversa: ");
    for (i = 2; i >= 0; i--) {
        printf("%c", a[i]);
    }
    printf("\n");

    return 0;
}
```

Acest cod îmbunătățit folosește `fgets` pentru a citi caracterele și gestionează mai bine erorile de intrare.

