---
nav-order: 5
title: Exerciții
parent: Structuri de date în limbajul Python
---

# Exerciții

1 Creați o listă selectând elemente de la indexuri impare din prima listă și elemente de la indexuri pare din a doua listă.

Având două liste, l1 și l2, scrieți un program pentru a crea o a treia listă, l3, selectând un element de la index impar din lista l1 și elemente de la indexuri pare din lista l2.

Date:
```python
l1 = [3, 6, 9, 12, 15, 18, 21]
l2 = [4, 8, 12, 16, 20, 24, 28]
```

Rezultat așteptat:
```css
Elementele de pe pozițiile cu index impar din prima listă:
[6, 12, 18]

Elementele de pe pozițiile cu index par din a doua listă:
[4, 12, 20, 28]

Afișarea listei finale a treia:
[6, 12, 18, 4, 12, 20, 28]
```

2 Tăiați lista în 3 bucăți egale și inversați fiecare bucată.

Date:
```python
sample_list = [11, 45, 8, 23, 14, 12, 78, 45, 89]
```
Rezultat așteptat:
```css
Bucată  1 [11, 45, 8]
După inversare [8, 45, 11]

Bucată  2 [23, 14, 12]
După inversare [12, 14, 23]

Bucată  3 [78, 45, 89]
După inversare [89, 45, 78]
```

3 Creați un set astfel încât să afișeze elementele din ambele liste în perechi.

Date: 
```python
first_list = [2, 3, 4, 5, 6, 7, 8]
second_list = [4, 9, 16, 25, 36, 49, 64]
```
Rezultat așteptat:
```css
Rezultatul este {(6, 36), (8, 64), (4, 16), (5, 25), (3, 9), (7, 49), (2, 4)}
```

4 Parcurgeți o listă dată și verificați dacă un element dat există ca valoare a unei chei într-un dicționar. În caz contrar, eliminați-le din listă.

Date:
```python
roll_number = [47, 64, 69, 37, 76, 83, 95, 97]
sample_dict = {'Jhon': 47, 'Emma': 69, 'Kelly': 76, 'Jason': 97}
```

Rezultat așteptat:
```css
După eliminarea elementelor nedorite din listă [47, 69, 76, 97]
```

5 Obțineți toate valorile din dicționar și adăugați-le la o listă, dar fără a adăuga duplicate.

Date:
```python
speed = {'ian': 47, 'feb': 52, 'martie': 47, 'aprilie': 44, 'mai': 52, 'iunie': 53, 'iulie': 54, 'aug': 44, 'sept': 54}
```
Rezultat așteptat:
```css
[47, 52, 44, 53, 54]
```

6 Eliminați duplicatele dintr-o listă, creați un tuplu și găsiți valorile minime și maxime.

Date:
```python
sample_list = [87, 45, 41, 65, 94, 41, 99, 94]
```
Rezultat așteptat:
```css
elemente unice [87, 45, 41, 65, 99]
tuplu (87, 45, 41, 65, 99)
minim: 41
maxim: 99
```