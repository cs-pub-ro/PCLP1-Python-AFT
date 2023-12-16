---
nav_order: 13
title: Recapitulare 3
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

# Recapitulare 3

## Caractere duplicate

Dat fiind un șir de caractere, găsiți toate caracterele duplicate.

Exemplu 1:
```python
Input : hello
Output : l
```

Exemplu 2:

```python
Input : geeksforgeeeks
Output : e g k s
```

## Cheia cu cele mai multe valori unice

Având un dicționar cu o listă de valori, extragți cheia a cărei valoare are cele mai multe valori unice.


Exemplu 1:
```python
Input : test_dict = {"Gfg" : [5, 7, 9, 4, 0], "is" : [6, 7, 4, 3, 3], "Best" : [9, 9, 6, 5, 5]} 
Output : "Gfg" 
Explanation : "Gfg" are 5 elemente unice
```

Exemplu 2:

```python
Input : test_dict = {"Gfg" : [5, 7, 7, 7, 7], "is" : [6, 7, 7, 7], "Best" : [9, 9, 6, 5, 5]} 
Output : "Best" 
Explanation : 3 (max) elemente unice: 9, 6, 5 ale cheii "Best".
```

## Prelucrarea datelor în format CSV

Scrieți un program Python care să citească date dintr-un fișier CSV într-un dicționar Python și să efectueze câteva operații cu acele date. Puteți utiliza biblioteca `csv` din Python pentru a facilita citirea din fișierul CSV.

Fișierul CSV are următoarea structură
```csv
NUME,Prenume,ID Student,Punctaj Tema,Data Submisie
POPESCU,Ionel,ionel.popescu,80,2023-12-14
PERFECT,Student,student.perfect,100,2023-12-04
IONESCU,Maria,student.perfect,100,2023-12-07
STOICA,Ioana,student.perfect,100,2023-12-05
POPA,Andrei,student.perfect,30,2023-12-10
STOIAN,Grigore,student.perfect,100,2023-12-15
```

Data submisiei este de forma `yyyy-mm-dd`.
Astfel, data `2023-12-14` înseamnă 14 Decembrie 2023.

Cernițe:
  1. Citiți fișierul CSV și creați un dicționar care reține informațiile pentru fiecare student din fișierul CSV.
  Cheia dicționarului va fi `ID Student` iar valoarea va fi un obiect care conține câmpurile: `nume_complet` (obținut prin operația `prenume + nume`), `punctaj_tema`, `data_submisie`, `punctaj_final`.
  1. Deadline-ul temei a fost pe data de 7 Dec 2023 (`2023-12-07`).
  Dacă un student a trimis o temă mai devreme de deadline, primește 10 puncte bonus pentru fiecare zi.
  Dacă un student a trimis tema după deadline, primește o depunctare de 10 puncte pentru fiecare zi de întârziere.
  Calculați în câmpul `punctaj_final` punctajul obținut de către fiecare student pentru tema sa.
  1. Ajustați punctajul final ar fiecărui student ținând cont de următoarea regulă: un student nu poate obține punctaj negativ pentru temă, punctajul minim fiind 0.
  1. Ajustați punctajul final ar fiecărui student ținând cont de următoarea regulă: se pot acorda maxim 30 de puncte bonus.
  1. Ajustați punctajul final ar fiecărui student ținând cont de următoarea regulă: deadline-ul hard a fost pe data de 14 Dec 2023 (`2023-12-14`); orice temă trimisă după această dată are punctajul 0.

**Rezultatele prelucrării, după fiecare subpunct, trebuie scrise într-un fișier, în format JSON.**

### Exemplu citire fișier CSV
```python
import csv

def read_csv_to_dictionary(file_path):
    """
    Citeste datele dintr-un fișier CSV într-un dicționar Python.
    """
    data_dictionary = {}

    try:
        with open(file_path, 'r') as csv_file:
            csv_reader = csv.DictReader(csv_file)
            for row in csv_reader:
                # Assume the CSV file has columns 'key' and 'value'
                key = row['key']
                value = row['value']
                
                # Add key-value pair to the dictionary
                data_dictionary[key] = value

    except FileNotFoundError:
        print(f"Fisierul CSV {file_path} nu a fost gasit.")
    except Exception as e:
        print(f"O eroare a aparut: {e}")

    return data_dictionary
```

### Exemplu scriere fișier JSON

```python
import json

# Scrie dicționarul în fișierul JSON
with open(file_path, 'w') as json_file:
    json.dump(my_dict, json_file, indent=4)
```