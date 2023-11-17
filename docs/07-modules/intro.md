---
nav_order: 7
title: Module în Python
has_children: true
---

# Module în Python

Modulele în Python sunt ca niște containere pentru a organiza și a separa codul în fișiere separate. Ele permit o structură mai clară a proiectului și reutilizarea mai ușoară a codului în diferite părți ale proiectului sau chiar în alte proiecte.

## Principii Cheie despre Module în Python

### Structura și Utilizarea Modulelor

- **Fișiere Separate:** Modulele sunt definite în fișiere Python individuale, fiecare reprezentând un modul distinct.
- **Elemente Definite în Module:** Pot conține funcții, clase, variabile sau alte elemente, toate organizate în spațiul lor de nume.

### Crearea și Importarea unui Modul

- **Crearea unui Modul:** Definiți funcții, clase sau variabile într-un fișier Python separat și salvați-l cu extensia `.py`.
- **Importarea unui Modul:** Utilizați instrucțiunea `import` pentru a accesa și folosi funcțiile, clasele sau variabilele definite în acel modul.

Exemplu simplu:
```python
# module.py - Modulul definit
def salut():
    print("Salut din modul!")

# main.py - Fișierul principal care importă modulul
import module

module.salut()  # Va afișa "Salut din modul!"
```

#### 3. Importuri Avansate și Gestionarea Modulelor:
- **Aliasuri pentru Module:** Puteți crea aliasuri pentru module pentru a evita conflictele de nume sau pentru a reduce lungimea codului.
- **Importuri Selective:** Puteți importa doar anumite elemente din module (`from module import function`) sau toate elementele (`from module import *`).
- **Importuri Parțiale:** Puteți importa elemente cu aliasuri (`from module import function as alias_function`).

Exemplu:
```python
# Importare cu alias și importuri selective
import module as mod
from module import salut as hello

mod.salut()    # Folosind aliasul pentru a apela funcția din modul
hello()        # Folosind funcția importată selectiv cu alias
```

#### 4. Modulele Încorporate în Python:
- Python vine cu module încorporate precum `math`, `os`, `random`, etc., care oferă funcționalități specifice pentru diverse operațiuni.
- Aceste module sunt accesate prin importare și permit executarea diferitelor operațiuni fără a rescrie codul de la zero.

Exemplu:
```python
import math

print(math.pi)  # Accesând constanta 'pi' din modulul 'math'
```

### Exerciții:

#### Exercițiul 1: Creare și Utilizare Modul

Creează un fișier numit `calcul.py` care să conțină o funcție `adunare(a, b)` ce returnează suma a două numere.

```python
# calcul.py
def adunare(a, b):
    return a + b
```

Aplicați apoi importul acestui modul în alt fișier (`main.py`) și utilizați funcția `adunare()` pentru a aduna două numere introduse de la tastatură.

#### Exercițiul 2: Utilizare de Aliasuri și Importuri Selective

Într-un modul, `utils.py`, definește două funcții: `salut()` și `adunare(a, b)`. Importă apoi aceste funcții folosind aliasuri și importuri selective într-un alt fișier.

```python
# utils.py
def salut():
    print("Salut!")

def adunare(a, b):
    return a + b
```

```python
# main.py
from utils import salut as hello, adunare

hello()  # Afișează "Salut!"
rezultat = adunare(5, 7)
print(rezultat)  # Afișează suma
```

Aceste exerciții sunt o modalitate excelentă de a înțelege conceptele de bază ale modulelor și modul în care acestea pot fi utilizate pentru organizarea și reutilizarea codului în Python.