---
nav_order: 12
title: Recapitulare 2
has_children: false
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC 
{:toc}
</details>

# Recapitulare 2

## Element majoritar

Dată fiind o serie de numere întregi sortate în ordine ne-descrescătoare, există exact un număr întreg în serie care apare mai mult de 25% dintre ori. Returnați acel număr întreg.

Exemplu 1:

Intrare: arr = [1,2,2,6,6,6,6,7,10]

Ieșire: 6

Exemplu 2:

Intrare: arr = [1,1]

Ieșire: 1

Restricții:

- 1 <= lungimea arr <= 104
- 0 <= arr[i] <= 105

## Numar de meciuri intr-un turneu

Ți se dă un număr întreg n, reprezentând numărul de echipe într-un turneu cu reguli ciudate:

Dacă numărul curent de echipe este par, fiecare echipă se asociază cu o altă echipă. Se joacă un total de n / 2 partide, iar n / 2 echipe avansează la următoarea rundă.
Dacă numărul curent de echipe este impar, o echipă avansează aleator în turneu, iar celelalte echipe se asociază între ele. Se joacă un total de (n - 1) / 2 partide, iar (n - 1) / 2 + 1 echipe avansează la următoarea rundă.
Returnați numărul de partide jucate în turneu până când este decis un câștigător.

Exemplu 1:

Intrare: n = 7

Ieșire: 6

Explicație:

```text
Detalii despre turneu:
- Runda 1: Echipe = 7, Partide = 3, și 4 echipe avansează.
- Runda 2: Echipe = 4, Partide = 2, și 2 echipe avansează.
- Runda 3: Echipe = 2, Partide = 1, și o echipă este declarată câștigătoare.
Numărul total de partide = 3 + 2 + 1 = 6.
```
Exemplu 2:

Intrare: n = 14

Ieșire: 13

Explicație:

```text
Detalii despre turneu:
- Runda 1: Echipe = 14, Partide = 7, și 7 echipe avansează.
- Runda 2: Echipe = 7, Partide = 3, și 4 echipe avansează.
- Runda 3: Echipe = 4, Partide = 2, și 2 echipe avansează.
- Runda 4: Echipe = 2, Partide = 1, și o echipă este declarată câștigătoare.
Numărul total de partide = 7 + 3 + 2 + 1 = 13.
```

## Cel mai mare numar impar

Ți se dă un șir de caractere `num`, care reprezintă un număr întreg mare. Returnează cel mai mare număr impar (sub formă de șir) care este un subșir nevid a lui num, sau un șir gol "" dacă nu există niciun număr impar.

Un subșir este o secvență contiguă de caractere într-un șir.

Exemplu 1:

Intrare: num = "52"

Ieșire: "5"

Explicație: Singurele subșiruri nevide sunt "5", "2" și "52". "5" este singurul număr impar.

Exemplu 2:

Intrare: num = "4206"

Ieșire: ""

Explicație: Nu există numere impare în "4206".

Exemplu 3:

Intrare: num = "35427"

Ieșire: "35427"

Explicație: "35427" este deja un număr impar.

Restricții:

- 1 <= lungimea num <= 105
- num constă doar din cifre și nu conține niciun zero înainte.

## Numar palindrom

Verificati ca un numar dat este palindrom.
Un numar este palindrom daca indiferent daca il citim de la stanga la dreapta sau de la dreapta la stanga are aceeasi valoare.

Exemplu:

```text
121 - palindrom
123 - nepalindrom
12321 - palindrom
12321 - nepalindrom
```

## Radacinile functiei de gradul al doilea

Dandu-se coeficientii `a`, `b` si `c` ale unei functii de gradul al 2-lea de forma `ax^2 + bx + c`, calculati radacinile acestei functii sau aruncati o exceptie pentru cazul in care functia nu are radacini reale.

## Incrementare cu 1

Se da un număr întreg mare reprezentat ca un șir de cifre, unde fiecare digits[i] este a i-a cifră a întregului. Cifrele sunt ordonate de la cea mai semnificativă la cea mai puțin semnificativă în ordine de la stânga la dreapta. Numărul mare nu conține niciun 0 înainte.

Incrementează numărul mare cu unu și returnează rezultatul sub formă de șir de cifre.

Exemplu 1:

Intrare: digits = [1,2,3]

Ieșire: [1,2,4]

Explicație: Șirul reprezintă întregul 123. Incrementarea cu unu dă 123 + 1 = 124. Prin urmare, rezultatul ar trebui să fie [1,2,4].

Exemplu 2:

Intrare: digits = [4,3,2,1]

Ieșire: [4,3,2,2]

Explicație: Șirul reprezintă întregul 4321. Incrementarea cu unu dă 4321 + 1 = 4322. Prin urmare, rezultatul ar trebui să fie [4,3,2,2].

Exemplu 3:

Intrare: digits = [9]

Ieșire: [1,0]

Explicație: Șirul reprezintă întregul 9. Incrementarea cu unu dă 9 + 1 = 10. Prin urmare, rezultatul ar trebui să fie [1,0].

Restricții:

- 1 <= lungimea digits <= 100
- 0 <= digits[i] <= 9
- digits nu conține niciun 0 înainte.

## Urcat pe scari

Urcați o scară. Sunt necesare n trepte pentru a ajunge în vârf.

De fiecare dată puteți urca fie 1, fie 2 trepte. În câte moduri distincte puteți urca pe scară până în vârf?

Exemplu 1:


Intrare: n = 2

Ieșire: 2

Explicație:

```text
Există două moduri de a urca pe scară.
1. 1 treaptă + 1 treaptă
2. 2 trepte
```

Exemplu 2:

Intrare: n = 3

Ieșire: 3

Explicație: 

```text
Există trei moduri de a urca pe scară.
1. 1 treaptă + 1 treaptă + 1 treaptă
2. 1 treaptă + 2 trepte
3. 2 trepte + 1 treaptă
```

## Scoaterea elementelor care apar de mai multe de 2 ori

Având un șir de numere întregi `nums` sortate în ordine ne-descrescătoare, eliminați unele duplicatate în loc astfel încât fiecare element unic să apară cel mult de două ori. Ordinea relativă a elementelor trebuie să fie păstrată.

Deoarece în unele limbaje de programare este imposibil să schimbați lungimea șirului, rezultatul trebuie plasat în prima parte a șirului `nums`. Mai precis, dacă există k elemente după eliminarea duplicatelor, atunci primele k elemente ale șirului `nums` ar trebui să conțină rezultatul final. Nu contează ce lăsați dincolo de primele k elemente.

Returnați k după plasarea rezultatului final în primele k sloturi ale șirului `nums`.

Nu alocati spațiu suplimentar pentru un alt șir. Trebuie să faceți acest lucru modificând șirul de intrare pe loc, cu o memorie suplimentară de O(1).

Exemplu 1:

Intrare: nums = [1,1,1,2,2,3]

Ieșire: 5, nums = [1,1,2,2,3,.]

Explicație:

Funcția ta ar trebui să returneze k = 5, cu primele cinci elemente ale lui nums fiind 1, 1, 2, 2 și 3, respectiv. Nu contează ce lăsați dincolo de k-ul returnat (de aceea sunt linii de jos).

Exemplu 2:

Intrare: nums = [0,0,1,1,1,1,2,3,3]

Ieșire: 7, nums = [0,0,1,1,2,3,3,.,.]

Explicație:

Funcția ta ar trebui să returneze k = 7, cu primele șapte elemente ale lui nums fiind 0, 0, 1, 1, 2, 3 și 3, respectiv. Nu contează ce lăsați dincolo de k-ul returnat (de aceea sunt puncte in loc de valori).
