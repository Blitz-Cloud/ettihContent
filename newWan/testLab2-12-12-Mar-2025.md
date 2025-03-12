---
title: testLab2
date: 12-Mar-2025
description: 
tags: []
uniYearAndSemester: 12
---

### Aceasta varianta este mai complicata decat ce si a dorit domnul profesor la laborator.
Mai jos este prezentata eroare a carei existenta stiu ca exista:
- In cazul in care ca pin este introdus 123f, programul seteaza valoarea varibilei **pin** ca fiind 123. Inca nu stiu de existenta unei solutii prin care pot sa detectez aceasta eroare. **cin.fail()** nu este de ajuns in acest caz.

```c
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
  cout << "Afisarea puterilor consecutive ale unui nr citit" << endl;
  int nr, nr_initial;
  int pin, i = 1;
  cout << "Sa se introduca un numar de la tastura" << endl;
  cin >> nr;
  while (cin.fail())
  {
    cin.clear();
    cin.ignore();
    cin.get();
    cout << "Tocmai ai introdus litere, te rog sa intoduci numai cifre" << endl;
    cin >> nr;
  }
  nr_initial = nr;

  do
  {
    pin = 0;
    cout << nr_initial << "^" << i << "=" << nr << endl
         << endl;
    nr *= nr_initial;
    i++;
    cin.ignore();
    cout << "Sa se introduca pinul pentru a continua afisarea puterilor numarul " << nr_initial << endl;
    cout << "Pin:";
    cin >> pin;
    while (cin.fail())
    {
      cin.clear();
      cin.ignore();
      cout << "\nPinul nu poate sa contina litere.\nTe rog sa introduci din nou pinul" << endl;
      cout << "Pin:";
      cin >> pin;
    }
    cout << endl;
  } while (pin == 1234);
  cout << "Pinul este gresit" << endl;
  return 0;
}
```
### Mai jos este prezenta solutia fara alte ferivicari inutile, asa cum isi dorea domnul profesor.

```c
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
  cout << "Afisarea puterilor consecutive ale unui nr citit" << endl;
  int nr, nr_initial;
  int pin, i = 1;
  cout << "Sa se introduca un numar de la tastura" << endl;
  cin >> nr;
  nr_initial = nr;

  do
  {
    pin = 0;
    cout << nr_initial << "^" << i << "=" << nr << endl
         << endl;
    nr *= nr_initial;
    i++;
    cin.ignore();
    cout << "Sa se introduca pinul pentru a continua afisarea puterilor numarul " << nr_initial << endl;
    cout << "Pin:";
    cin >> pin;
    cout << endl;
  } while (pin == 1234);
  cout << "Pinul este gresit" << endl;
  return 0;
}
```


