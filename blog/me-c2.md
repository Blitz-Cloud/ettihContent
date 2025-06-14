---
title: Me curs 2 eng
date: "29-May-2025"
description: "Clasele nu sunt terminate iar codul in linii mari este menit sa fie utilizat ca un model pentru o implementare proprie"
tags: ["facultate", "materiale"]
---

### Perfect! Sa rezolvam problema S2.1 pas cu pas.

**(a) Calculul concentratiei electronilor de conductie**

Stim ca sodiul metalic are o structura cubica cu corp centrat (bcc). Lungimea laturii cubului este \( a = 4.25 \cdot 10^{-8} \text{ cm} \). Fiecare atom de sodiu contribuie cu un electron de conductie. O celula elementara bcc contine 2 atomi.

Pentru a calcula concentratia \( n \) (numarul de electroni pe unitate de volum), vom folosi formula:

$$ n = \frac{\text{numarul de atomi in celula elementara}}{\text{volumul celulei elementare}} $$

In cazul unei structuri bcc, avem 2 atomi per celula elementara, iar volumul celulei este \( V = a^3 \). Astfel,

$$ n = \frac{2}{a^3} $$

Acum, inlocuim valoarea lui \( a \) (avand grija sa convertim cm in \(m^3\)):
\(a = 4.25 \cdot 10^{-8} \text{ cm} = 4.25 \cdot 10^{-10} \text{ m} \)

$$ n = \frac{2}{(4.25 \cdot 10^{-10} \text{ m})^3} $$

$$ n = \frac{2}{7.676 \cdot 10^{-29} \text{ m}^3} $$

$$ n \approx 2.605 \cdot 10^{28} \text{ m}^{-3} $$

Deci, concentratia electronilor de conductie in sodiu este aproximativ \( 2.605 \cdot 10^{28} \text{ m}^{-3} \).

**(b) Derivarea expresiei pentru energia Fermi**

Acum, vom deriva expresia pentru energia Fermi \( E_F \) folosind modelul electronilor liberi. Stim ca, la temperatura de 0 K, toti electronii ocupa starile cu energie pana la energia Fermi. Numarul total de electroni \( N \) este dat de:

$$ N = \int_0^{E_F} g(E) dE $$

Unde \( g(E) \) este densitatea de stari, care, in modelul electronilor liberi, este:

$$ g(E) = \frac{V}{2\pi^2} \left( \frac{2m}{\hbar^2} \right)^{3/2} E^{1/2} $$

Unde:

- \( V \) este volumul cristalului
- \( m \) este masa electronului
- \( \hbar \) este constanta Planck redusa

Integram densitatea de stari de la 0 pana la \( E_F \):

$$ N = \int_0^{E_F} \frac{V}{2\pi^2} \left( \frac{2m}{\hbar^2} \right)^{3/2} E^{1/2} dE $$

$$ N = \frac{V}{2\pi^2} \left( \frac{2m}{\hbar^2} \right)^{3/2} \int_0^{E_F} E^{1/2} dE $$

$$ N = \frac{V}{2\pi^2} \left( \frac{2m}{\hbar^2} \right)^{3/2} \frac{2}{3} E_F^{3/2} $$

Stim ca densitatea \( n = \frac{N}{V} \), asa ca putem rescrie ecuatia:

$$ n = \frac{1}{3\pi^2} \left( \frac{2m}{\hbar^2} \right)^{3/2} E_F^{3/2} $$

Acum, rezolvam pentru \( E_F \):

$$ E_F^{3/2} = 3\pi^2 n \left( \frac{\hbar^2}{2m} \right)^{3/2} $$

$$ E_F = \frac{\hbar^2}{2m} (3\pi^2 n)^{2/3} $$

Observam ca energia Fermi \( E_F \) depinde doar de constanta Planck redusa \( \hbar \), de concentratia electronilor \( n \) si de masa electronului \( m \). Nu depinde de caracteristicile cristalului in sine, ci doar de concentratia electronilor liberi.

**Concluzie**

- Concentratia electronilor de conductie in sodiu este aproximativ \( 2.605 \cdot 10^{28} \text{ m}^{-3} \).
- Energia Fermi pentru modelul electronilor liberi este \( E_F = \frac{\hbar^2}{2m} (3\pi^2 n)^{2/3} \), si depinde doar de concentratia electronilor si de constante fundamentale, nu de masa cristalului.

Am reusit sa rezolvam problema S2.1. Vrei sa trecem la urmatoarea problema sau ai nevoie de clarificari suplimentare?

</br>

### Sigur, sa rezolvam problema S2.2.

**Problem S2.2** For an intrinsic semiconductor, having a density of electron states of \(2 \cdot 10^{21} (\text{cm}^{-3} \text{eV}^{-1})\) and a bandgap energy of 1.5 eV:

(a) Find the position of the Fermi level with respect to the valence and conduction bands;

(b) Estimate the number of conduction band electrons at room temperature.

It is known that an intrinsic semiconductor is characterized by the same number of electrons in the conduction band and of holes in the valence band.

**Solution**

**(a) Finding the position of the Fermi level**

Intr-un semiconductor intrinsic, numarul de electroni din banda de conductie este egal cu numarul de goluri din banda de valenta. Datorita acestei simetrii, nivelul Fermi se afla, in general, la mijlocul benzii interzise (bandgap).

Astfel, pozitia nivelului Fermi \( E_F \) este la mijlocul distantei dintre varful benzii de valenta \( E_V \) si baza benzii de conductie \( E_C \).

$$ E_F = \frac{E_C + E_V}{2} $$

Daca definim \( E_V = 0 \) (varful benzii de valenta ca origine), atunci \( E_C = E_g = 1.5 \text{ eV} \), unde \( E_g \) este energia benzii interzise.

$$ E_F = \frac{1.5 \text{ eV} + 0}{2} = 0.75 \text{ eV} $$

Deci, nivelul Fermi se afla la 0.75 eV deasupra varfului benzii de valenta.

**(b) Estimating the number of conduction band electrons at room temperature**

Numarul de electroni din banda de conductie poate fi estimat folosind aproximarea Boltzmann. Concentratia electronilor in banda de conductie \( n \) este data de:

$$ n = N_C \exp \left( -\frac{E_C - E_F}{k_B T} \right) $$

unde:

- \( N_C \) este densitatea efectiva de stari in banda de conductie. Aceasta nu este data direct, dar putem folosi densitatea de stari mentionata in problema si aproximatia Boltzmann pentru a gasi \( n \).

- \( E_C - E_F \) este diferenta de energie intre baza benzii de conductie si nivelul Fermi, care este \( 0.75 \text{ eV} \).

- \( k_B \) este constanta Boltzmann (\( 8.617 \times 10^{-5} \text{ eV/K} \)).

- \( T \) este temperatura in Kelvin (aproximativ 300 K la temperatura camerei).

Avand in vedere densitatea de stari data, vom aproxima \( N_C \) folosind aceasta valoare si integrarea Boltzmann.

Densitatea de stari data este \( Z(E) = 2 \times 10^{21} \text{ cm}^{-3} \text{ eV}^{-1} \)

Vom integra aceasta densitate in apropierea benzii de conductie, folosind diferenta de energie \( E_C - E_F = 0.75 \text{ eV} \) si aproximarea Boltzmann:

$$ n = \int\_{E_C}^{\infty} Z(E) \exp \left( -\frac{E - E_F}{k_B T} \right) dE $$
Aproximam \( Z(E) \) constant in apropierea marginii benzii de conductie \( Z(E) = 2 \times 10^{21} \text{ cm}^{-3} \text{ eV}^{-1} \).

$$ n = Z(E) \int\_{E_C}^{\infty} \exp \left( -\frac{E - E_F}{k_B T} \right) dE = Z(E) k_B T \exp \left( -\frac{E_C - E_F}{k_B T} \right) $$

Calculam \( k_B T \) la 300 K:

$$ k_B T = (8.617 \times 10^{-5} \text{ eV/K}) \cdot (300 \text{ K}) \approx 0.02585 \text{ eV} $$

$$ n = (2 \times 10^{21} \text{ cm}^{-3} \text{ eV}^{-1}) \cdot (0.02585 \text{ eV}) \cdot \exp \left( -\frac{0.75 \text{ eV}}{0.02585 \text{ eV}} \right) $$

$$ n \approx (5.17 \times 10^{19} \text{ cm}^{-3}) \cdot \exp(-29.01) $$

$$ n \approx 5.17 \times 10^{19} \cdot 3.5 \times 10^{-13} \text{ cm}^{-3} \approx 1.81 \times 10^{7} \text{ cm}^{-3} $$

Asadar, numarul estimat de electroni in banda de conductie la temperatura camerei este aproximativ \( 1.81 \times 10^{7} \text{ cm}^{-3} \).

**Concluzie**

- Pozitia nivelului Fermi este la \( 0.75 \text{ eV} \) deasupra varfului benzii de valenta.
- Numarul estimat de electroni in banda de conductie la temperatura camerei este aproximativ \( 1.81 \times 10^{7} \text{ cm}^{-3} \).

Am reusit sa rezolvam si aceasta problema. Trecem la urmatoarea?
