---
title: ecuatiaDeGradul2
date: 12-Mar-2025
description: 
tags: []
uniYearAndSemester: 12
---

#### Atentie acest cod a fost scris pentru a functiona pe Linux, recomand sa se elimine **system("clear")** pentru a asigura functionarea programului.

Ce face **system("clear"):
1. Aceasta are acelasi rol ca functia *clrscr()* din biblioteca *conio*(care nu biblioteca suportata in varianta oficiala de cpp
2. In terminalul din Linux comanda *clear* are rolul de a curata ecranul, aceasta fiind similara cu combinatia de taste *<CTRL>+L*.
3. Din ceea ce stiu desi asta poate sa difere, in PowerShell cu ajutorul  comenzii *clear* poti obtine accelasi lucru, iar pentru Command Prompt exista commanda *cls*. Nu imi este foarte clar care este procesator de commenzi prestabilit in Windows. Documenzatia pentru instructiunea *system()* din cpp [aici](https://en.cppreference.com/w/cpp/utility/program/system)

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
  cout << "Rezolvarea ecuatiei de gradul 2" << endl;
  char opt;
  float x, x1, x2, a, b, c, d;

  do
  {
    system("clear");
    cout << "Acest program este destinat sa rezolve ecuatia de gradul al doilea.\nAceasta are forma ax^2+bx+c=0" << endl;
    cout << "Sa se introduca valorile pentru a,b si c in oridinea in care sunt cerute" << endl;
    cout << "a=";
    cin >> a;
    cout << "b=";
    cin >> b;
    cout << "c=";
    cin >> c;

    d = b * b - 4 * a * c;
    if (d > 0)
    {
      x1 = (-1 * b + sqrt(d)) / 2 * a;
      x2 = (-1 * b - sqrt(d)) / 2 * a;
      cout << "x1=" << x1 << endl;
      cout << "x2=" << x2 << endl;
    }
    else if (d < 0)
    {
      x1 = -b / 2 * a;
      x2 = sqrt(-1 * d) / 2 * a;
      cout << "x1=" << x1 << "+ i*" << x2 << endl;
      x1 = -b / 2 * a;
      x2 = sqrt(-1 * d) / 2 * a;
      cout << "x2=" << x1 << "- i*" << x2 << endl;
    }
    else
    {
      x = -b / 2 * a;
    }
    cout << "Daca se mai dorescte o interogare sa se introduca d pentru a opri programul tasteaza n" << endl;
    cin >> opt;
    while (opt != 'd' && opt != 'n')
    {
      cin.ignore();
      cout << "Optiune invalida, sa se introduca d sau n" << endl;
      cin >> opt;
    }
  } while (opt != 'n');
  return 0;
}
```


