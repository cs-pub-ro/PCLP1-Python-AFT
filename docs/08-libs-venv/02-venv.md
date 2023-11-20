---
nav_order: 2
title: Mediul de Dezvoltare Virtual (Virtual Environment)
parent: Instalarea bibliotecilor și utilizarea mediilor virtuale
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Mediul de Dezvoltare Virtual (Virtual Environment)

Mediul de dezvoltare virtual (virtual environment) în Python este o metodă care rezolvă problema gestionării dependențelor și a versiunilor diferite ale pachetelor în cadrul proiectelor Python. Acesta oferă un spațiu izolat și independent în care puteți instala biblioteci și pachete Python fără a afecta instalările globale sau alte proiecte.

## Când este necesar un mediu de dezvoltare virtual?

1. **Proiecte cu dependențe diferite:** Când lucrați la mai multe proiecte care necesită versiuni diferite ale acelorași pachete sau chiar pachete incompatibile între ele, mediile virtuale vă permit să izolați și să gestionați aceste dependențe specifice pentru fiecare proiect în parte.

2. **Evitarea conflictelor între biblioteci:** Unele proiecte pot necesita versiuni specifice ale bibliotecilor sau chiar biblioteci care nu sunt compatibile între ele. Mediile virtuale vă permit să evitați conflictele între aceste dependențe, oferind un spațiu izolat pentru fiecare proiect.

## Avantajele utilizării mediului de dezvoltare virtual:

1. **Izolare și independență:** Fiecare mediu virtual are propria sa instanță Python și pachete instalate, ceea ce înseamnă că modificările efectuate într-un mediu nu afectează alte medii sau instalările globale.

2. **Gestionarea mai ușoară a dependențelor:** Puteți gestiona și instala pachete specifice pentru fiecare proiect, fără a crea conflicte între versiunile de pachete.

3. **Experimentare și testare:** Mediile virtuale permit să testați diferite configurații și pachete fără a afecta proiectele principale sau mediul de lucru global.

## Exemplu de utilizare a unui mediu de dezvoltare virtual:

1. **Crearea unui mediu virtual:**

   Utilizând `virtualenv`, puteți crea un mediu virtual cu comanda:
   ```bash
   virtualenv nume_mediu_virtual
   ```

2. **Activarea și utilizarea mediu virtual:**

   Pe sistemele Windows:
   ```bash
   nume_mediu_virtual\Scripts\activate
   ```

   Pe sistemele Unix (MacOS și Linux):
   ```bash
   source nume_mediu_virtual/bin/activate
   ```

3. **Instalarea și utilizarea pachetelor în mediuul virtual:**

   În mediuul activat, puteți instala pachete folosind `pip`:
   ```bash
   pip install nume_bibliotecă
   ```

   Pachetele instalate vor fi disponibile doar în cadrul mediului virtual activat și nu vor afecta instalările globale.

Mediile de dezvoltare virtuale sunt esențiale pentru dezvoltarea Python, oferind un mod organizat și izolat de a gestiona dependențele și versiunile diferite ale pachetelor pentru fiecare proiect în parte. Acestea facilitează dezvoltarea, testarea și menținerea proiectelor fără a crea conflicte între dependențe și versiuni.

## Exerciții

Puteți utiliza instrumente precum `virtualenv` sau `venv` în Python.

1. Creați un mediu virtual numit "myenv".
Activeați-l și Afișați calea către interpretorul Python din mediu.

1. Creează un mediu virtual numit "libenv".
Activați mediul virtual și instalați versiunea 2.15.1 a bibliotecii `requests`.
Apoi afișați toate bibliotecile instalate în mediu.

1. În mediu virtual "libenv", creați un fișier de cerințe numit "requirements.txt".
Adăugați următoarele biblioteci și versiuni în acest fșier și apoi instalați-le:

- biblioteca `numpy` cu versiunea minimă 1.24.0
- biblioteca `requests` cu versiunea fixă 2.28.1
- biblioteca `matplotlib` cu ultima versiune disponibilă

4. Creați un script în acest mediu virtual care importă biblioteca `numpy`.
Cu aceasta, creați un vector de 10 elemente aleatoare între 0 și 100 și (folosind `numpy.random.randint()`) și desenați graficul acestora folosind `matplotlib`.
Apoi afișați la consolă următoarele statistici referitoare la vectorul creat anterior:

- media
- mediana
- deviația standard
- minimul
- maximul
- suma

   Căutați în [documentația bibliotecii `numpy` despre array-uri](https://numpy.org/doc/1.24/reference/routines.html) câte o funcție care să calculeze fiecare dintre valorile de mai sus.
