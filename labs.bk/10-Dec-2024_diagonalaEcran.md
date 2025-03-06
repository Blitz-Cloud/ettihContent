---
title: diagonalaEcran
date: 10-Dec-2024
description: 
tags: []
---

```c
Acest cod este o colecție de funcții utilitare și un program principal care le demonstrează. Scopul principal este de a oferi funcționalități similare cu cele găsite în mediile DOS/Turbo C, dar pentru un sistem Unix-like (presupunând că rulează pe un terminal real, nu pe o consolă).

**Structura generală:**

1.  **Include-uri:** Include header-e standard C pentru funcții de timp, controlul terminalului, I/O, alocare de memorie, string-uri și erori.
2.  **Definiri de Macro-uri:** Definește macro-uri pentru:
    *   `CLRSCR()`: Șterge ecranul folosind comanda `system("clear")`.
    *   Coduri de culoare ANSI: Definește coduri de escape ANSI pentru a seta culoarea textului (`FG_...`) și a fundalului (`BG_...`).
    *   `BGFG_RESET`: Resetează culorile la valorile implicite.
    *   `GOTOXY(X, Y)`: Muta cursorul la coordonatele (X, Y) pe ecran folosind coduri de escape ANSI.
    *   `DELLINE(X, Y)`: Șterge o linie de text de la coordonatele (X, Y).
3.  **Funcții utilitare:**
    *   `myfflush()`:  O funcție de flush a buffer-ului de intrare standard. Folosește `dup`, `tcdrain`, `tcflush` și `close` pentru a asigura că toate datele sunt scrise și buffer-ul este golit.
    *   `mygetchar()`: Citește un caracter de la intrare standard, presupunând că terminalul este în modul "read-by-line".  Consumă și caracterul newline (`\n`).
    *   `getch()`: Citește un caracter fără a-l afișa pe ecran (fără echo). Folosește `termios` pentru a dezactiva modul canon și echo.
    *   `getche()`: Citește un caracter și îl afișează pe ecran (cu echo). Folosește `termios` pentru a dezactiva modul canon.
    *   `getche2()`: O altă implementare a `getche()`, folosind comenzi `stty` pentru a controla modul terminalului.
    *   `delay()`: Introduce o pauză în execuție pentru un număr specificat de milisecunde. Folosește `usleep` pentru întârzieri mai mici de 1 secundă și `nanosleep` pentru întârzieri mai mari.
    *   `kbhit()`: Verifică dacă s-a apăsat o tastă fără a bloca execuția. Folosește `termios` pentru a dezactiva modul canon și echo, și `fcntl` pentru a seta intrarea standard în mod non-blocant.
    *   `kbhit_wait()`: Blochează execuția până când se apasă o tastă. Folosește comenzi `stty` pentru a controla modul terminalului.
    *   `rotr()`: Rotește un număr întreg fără semn la dreapta cu un număr specificat de poziții.
    *   `rotl()`: Rotește un număr întreg fără semn la stânga cu un număr specificat de poziții.
    *   `printb()`: Afișează reprezentarea binară a unui număr întreg fără semn.
4.  **Funcția `main()`:**
    *   Șterge ecranul.
    *   Inițializează generatorul de numere aleatoare.
    *   Afișează un număr aleatoriu generat.
    *   Afișează text colorat folosind codurile de escape ANSI definite.
    *   Demonstrează utilizarea funcțiilor `getch()` și `getche()` pentru citirea caracterelor.
    *   Citește o parolă de 4 caractere folosind `getch()` și afișează asteriscuri în loc de caracterele introduse.
    *   Afișează reprezentarea binară a unui număr, apoi a numărului rotit la dreapta și la stânga.
    *   Așteaptă apăsarea unei taste folosind `kbhit()` într-o buclă.

**Funcționalități cheie și observații:**

*   **Controlul terminalului:** Codul folosește intens funcțiile `termios` și comenzi `stty` pentru a controla modul terminalului.  Acest lucru este necesar pentru a implementa funcții precum `getch()`, `getche()` și `kbhit()`, care necesită citirea caracterelor fără a aștepta un newline și fără a le afișa pe ecran.
*   **Coduri de escape ANSI:**  Utilizarea codurilor de escape ANSI permite controlul culorilor textului și a fundalului, precum și poziționarea cursorului pe ecran.
*   **Funcții de temporizare:** Funcția `delay()` oferă o modalitate de a introduce pauze în execuție.
*   **Portabilitate:**  Codul este specific sistemelor Unix-like și depinde de funcțiile `termios`, `fcntl`, `usleep`, `nanosleep` și de comanda `system("clear")`.  Nu va funcționa pe Windows fără modificări semnificative.
*   **Comentarii:** Comentariile din cod sunt utile și explică scopul fiecărei funcții.
*   **Testare:** Comentariul inițial menționează că funcțiile au fost testate doar pe terminale reale, nu pe console. Acest lucru sugerează că ar putea exista probleme de compatibilitate cu unele emulatoare de terminal.
*   **Encoding:**  Codul menționează suport doar pentru encoding ASCII.

**În concluzie:**

Acest cod este o colecție de funcții utilitare care oferă funcționalități de control al terminalului, citire de caractere, temporizare și manipulare de biți.  Este util pentru a crea aplicații de consolă interactive pe sisteme Unix-like, dar nu este portabil pe Windows fără modificări.  Funcția `main()` demonstrează utilizarea acestor funcții.

```
