---
nav_order: 3
title: Module Implicite în Python
parent: Module în Python
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Modulele Implicite în Python

În Python, modulele implicite sunt modulele încorporate în limbajul însuși sau cele care vin preinstalate odată cu distribuția standard Python. Acestea oferă funcționalități diverse și sunt disponibile pentru a fi utilizate fără a fi necesară instalarea suplimentară a altor pachete sau module externe.

## Exemple de Module Implicite

- **`math`:** Furnizează funcții matematice și constante pentru operații matematice avansate.
- **`random`:** Oferă funcții pentru generarea de numere aleatoare.
- **`os`:** Asigură funcționalități pentru interacțiunea cu sistemul de operare, precum manipularea fișierelor și directoarelor.
- **`datetime`:** Permite lucrul cu date și timp.
- **`sys`:** Furnizează funcționalități specifice sistemului și interacțiunea cu interpreterul Python.

## Utilizarea Modulelor Implicite

- **Importul Direct:** Aceste module sunt importate direct în codul tău fără a fi nevoie de instalare suplimentară sau de descărcare de pachete.
- **Accesarea Funcțiilor și Constantelor:** După import, funcțiile, constantele și metodele din aceste module sunt disponibile pentru a fi utilizate în programul tău.

Exemplu de utilizare a unui modul implicit (`math`):

```python
import math

print(math.pi)  # Accesând constanta 'pi' din modulul 'math'
print(math.sqrt(16))  # Utilizând funcția 'sqrt' din modulul 'math'
```

## Exerciții

Importați modulul `random`.

1. Folosind [documentația](https://docs.python.org/3/library/random.html), apelați una sau mai multe funcții din modul astfel încât să obțineți o listă de 10 numere aleatoare între 10 și 100 și divizibile cu 5.
Afișați apoi lista.

1. Tot cu ajutorul [documentației](https://docs.python.org/3/library/random.html), generați o parolă formată dintr-un număr aleator de litere (între 10 și 20) mari sau mici.
Vă puteți folosi și de modulul impliciti [`string`](https://docs.python.org/3/library/string.html).

1. Scrieți o funcție numită `diferenta_zilelor` care primește două argumente de tipul `datetime` și returnează diferența în zile dintre cele două date.

    Exemplu de utilizare:
    ```python
    import datetime

    data1 = datetime.datetime(2023, 11, 15)
    data2 = datetime.datetime(2023, 11, 21)

    print(diferenta_zilelor(data1, data2))  # Ar trebui să afișeze 6
    ```

1. Scrieți o funcție numită `frecventa_elementelor` care primește o listă și returnează un dicționar în care cheile sunt elementele unice din listă și valorile reprezintă frecvența fiecărui element în listă.

    Exemplu de utilizare:
    ```python
    print(frecventa_elementelor([1, 2, 2, 3, 3, 3, 4, 4, 4, 4]))  
    # Ar trebui să afișeze {1: 1, 2: 2, 3: 3, 4: 4}
    ```

1. Folosind modulul `itertools`, scrieți o funcție numită `permutari` care primește o listă și returnează o listă de tuple reprezentând toate permutările posibile ale elementelor din listă.

    Exemplu de utilizare:
    ```python
    print(permutari(['a', 'b', 'c']))
    # Ar trebui să afișeze [('a', 'b', 'c'), ('a', 'c', 'b'), ('b', 'a', 'c'), ('b', 'c', 'a'), ('c', 'a', 'b'), ('c', 'b', 'a')]
    ```
