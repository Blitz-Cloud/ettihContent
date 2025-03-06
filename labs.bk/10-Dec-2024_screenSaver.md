---
title: screenSaver
date: 10-Dec-2024
description: 
tags: []
---

```c
Acest cod este o colecție de funcții utilitare concepute pentru a lucra cu terminale, în special în medii unde funcționalitățile standard C nu sunt suficiente sau se comportă diferit (cum ar fi consolele virtuale vs. terminale reale). De asemenea, include funcții pentru manipularea biților și un exemplu de utilizare a acestor funcții.

**Analiză detaliată:**

1.  **Header-e incluse:**
    *   `<time.h>`: Pentru funcții legate de timp, cum ar fi `delay()` (implementată cu `nanosleep()` sau `usleep()`).
    *   `<termios.h>`: Esențial pentru manipularea atributelor terminalului (moduri canonice/non-canonice, echo, etc.).
    *   `<fcntl.h>`: Pentru controlul fișierelor, în special pentru a seta terminalul în mod non-blocant (`O_NONBLOCK`).
    *   `<unistd.h>`: Diverse funcții POSIX, inclusiv `usleep()`, `system()`, `read()`, `write()`, `dup()`, `close()`.
    *   `<stdio.h>`: Funcții standard de input/output (printf, getchar, getc, etc.).
    *   `<stdlib.h>`: Funcții diverse, inclusiv `system()`, `rand()`, `srand()`.
    *   `<string.h>`: Funcții de manipulare a șirurilor de caractere (memcpy, etc.).
    *   `<errno.h>`: Pentru gestionarea erorilor.

2.  **Definiri de macro-uri:**
    *   `CLRSCR()`: Șterge ecranul terminalului folosind comanda `clear`.
    *   `FG_*`, `BG_*`: Definiri pentru codurile de escape ANSI pentru a seta culoarea textului (foreground) și a fundalului (background).
    *   `BGFG_RESET`: Resetează culorile la valorile implicite.
    *   `GOTOXY(X, Y)`: Muta cursorul la coordonatele (X, Y) pe terminal folosind coduri de escape ANSI.
    *   `DELLINE(X, Y)`: Șterge linia de la coordonatele (X, Y).

3.  **Funcții:**

    *   `myfflush()`: O implementare personalizată a `fflush(stdin)`. Folosește `dup()`, `tcdrain()`, `tcflush()` și `close()` pentru a asigura că buffer-ul de intrare este golit. Este important de reținut că `fflush(stdin)` are un comportament nedefinit în standardul C, deci această implementare este mai sigură.

    *   `mygetchar()`: Citește un caracter de la intrare, presupunând că terminalul este în modul "read-by-line". Consumă caracterul newline (`\n`) după citirea caracterului dorit.

    *   `getch()`: Citește un caracter fără echo (nu se afișează pe ecran) și fără a aștepta un newline (mod non-canonic). Modifică temporar atributele terminalului folosind `termios`.

    *   `getche()`: Citește un caracter cu echo (se afișează pe ecran) și fără a aștepta un newline (mod non-canonic). Modifică temporar atributele terminalului folosind `termios`.

    *   `getche2()`: O altă variantă de `getche()`, care folosește comanda `stty raw` pentru a dezactiva newline-ul și `stty cooked` pentru a reveni la modul normal. Această abordare este mai simplă, dar depinde de disponibilitatea comenzii `stty`.

    *   `delay(long msec)`: Implementează o funcție de întârziere (delay) de `msec` milisecunde. Folosește `usleep()` pentru întârzieri mai mici de 1 secundă și `nanosleep()` pentru întârzieri mai mari sau egale cu 1 secundă. Gestionează, de asemenea, întreruperile (`EINTR`) în timpul `nanosleep()`.

    *   `kbhit()`: Verifică dacă s-a apăsat o tastă fără a bloca execuția programului (non-blocking). Folosește `termios` pentru a seta terminalul în mod non-canonic și `fcntl` pentru a-l seta în mod non-blocant. Dacă s-a apăsat o tastă, o pune înapoi în buffer-ul de intrare cu `ungetc()`.

    *   `kbhit_wait()`: Așteaptă până când se apasă o tastă (blocking). Folosește `stty raw` pentru a dezactiva newline-ul și `getch()` pentru a citi caracterul.

    *   `rotr(unsigned int nr, unsigned int pos)`: Realizează o rotație la dreapta (rotate right) a unui număr întreg fără semn `nr` cu `pos` poziții.

    *   `rotl(unsigned int nr, unsigned int pos)`: Realizează o rotație la stânga (rotate left) a unui număr întreg fără semn `nr` cu `pos` poziții.

    *   `printb(unsigned int nr)`: Afișează reprezentarea binară a unui număr întreg fără semn `nr`.

4.  **Funcția `main()`:**
    *   Șterge ecranul.
    *   Intră într-o buclă infinită care rulează până când se apasă o tastă.
    *   În interiorul buclei:
        *   Generează un număr aleatoriu între 0 și 19.
        *   Muta cursorul la coordonatele (nr, nr) pe ecran.
        *   Afișează textul "Windows" cu culoarea albastră.
        *   Așteaptă 200 de milisecunde.
        *   Șterge ecranul.
    *   Când se apasă o tastă, bucla se termină și programul se încheie.

**În rezumat:**

Acest cod oferă un set de instrumente pentru a controla terminalul, a citi input de la utilizator în moduri diferite (cu sau fără echo, blocant sau non-blocant), a manipula biți și a afișa informații colorate. Este util în special pentru aplicații care necesită un control fin asupra interacțiunii cu utilizatorul în terminal. Comentariile din cod indică faptul că a fost testat pe terminale reale, nu pe console virtuale, ceea ce sugerează că ar putea exista diferențe de comportament în diferite medii.

**Ce face programul principal (main):**

Programul principal șterge ecranul și apoi intră într-o buclă. În interiorul buclei, generează un număr aleatoriu între 0 și 19, mută cursorul la acea poziție pe ecran, afișează cuvântul "Windows" în albastru, așteaptă 200 de milisecunde și apoi șterge din nou ecranul. Acest lucru creează un efect de animație simplu, unde cuvântul "Windows" apare și dispare în locații aleatorii pe ecran. Bucla continuă până când utilizatorul apasă o tastă. Funcția `kbhit()` este folosită pentru a detecta dacă s-a apăsat o tastă fără a bloca execuția programului.

```
