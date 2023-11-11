---
title: Exerciții
parent: Expresii și instrucțiuni de control
nav_order: 3
---

# Exerciții

1. Calculați înmulțirea și suma a două numere
Având două numere întregi, returnați produsul lor doar dacă acesta este egal sau mai mic decât 1000. În caz contrar, returnați suma lor.

   ```python
   num1 = 20
   num2 = 30
   # Rezultatul afișat este 600
   ```

   ```python
   num1 = 40
   num2 = 30
   # Rezultatul afișat este 70
   ```

1. Afișați suma numărului curent și a celui anterior
Scrieți un program care iterează primele 10 numere și, în fiecare iterație, afișează suma numărului curent și a celui precedent.

   Rezultatul așteptat
   ```python
   Afișarea sumei numărului curent și a celui precedent într-un interval de la 0 la 9
   Număr curent 0 Număr precedent 0 Suma: 0
   Număr curent 1 Număr precedent 0 Suma: 1
   Număr curent 2 Număr precedent 1 Suma: 3
   Număr curent 3 Număr precedent 2 Suma: 5
   Număr curent 4 Număr precedent 3 Suma: 7
   Număr curent 5 Număr precedent 4 Suma: 9
   Număr curent 6 Număr precedent 5 Suma: 11
   Număr curent 7 Număr precedent 6 Suma: 13
   Număr curent 8 Număr precedent 7 Suma: 15
   Număr curent 9 Număr precedent 8 Suma: 17
   ```

1. Afișați caracterele dintr-un șir care sunt prezente la un număr de index par.
Scrieți un program pentru a accepta un șir de la utilizator și pentru a afișa caracterele care sunt prezente la un număr de index par.

   De exemplu, dacă avem șirul 'pynative', ar trebui să afișăm 'p', 'n', 't', 'v'."

1. Eliminați primele n caractere dintr-un șir de caractere.
Scrieți un program pentru a elimina caracterele dintr-un șir începând de la zero până la n și pentru a returna un șir nou.

   De exemplu:
   
   `remove_chars("pynative", 4)` astfel încât rezultatul să fie `tive`. Aici, trebuie să eliminăm primele patru caractere dintr-un șir.
   
   `remove_chars("pynative", 2)` astfel încât rezultatul să fie `native`. Aici, trebuie să eliminăm primele două caractere dintr-un șir.
   
   Notă: `n` trebuie să fie mai mic decât lungimea șirului.
   Dacă este mai mare, afișați un mesaj care informează despre acest lucru.

1. Verifică dacă primul și ultimul număr dintr-o listă sunt identice.
Scrie o funcție care să returneze True dacă primul și ultimul număr dintr-o listă dată sunt aceleași.
Dacă numerele sunt diferite, atunci returnează False.

   Definiți următoarele variabile
   ```python
   numbers_x = [10, 20, 30, 40, 10]
   numbers_y = [75, 65, 35, 75, 30]
   ```

   Pentru a itera prin elementele unei liste, folosiți construcția
   ```python
   for element in nume_lista:
       print(element)
   ```