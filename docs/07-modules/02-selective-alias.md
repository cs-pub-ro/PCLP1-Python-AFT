---
nav_order: 2
title: Importuri Selective și Aliasuri
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

# Importuri Selective și Aliasuri

## Importurile Selective

- **Utilizarea `from module import ...`:** Această formă de import vă permite să importați doar anumite elemente (funcții, clase sau variabile) dintr-un modul, fără a importa totul.

Exemplu de import selectiv:

```python
# Import selectiv dintr-un modul
from math import pi, sqrt

print(pi)    # Accesând constanta 'pi' direct
print(sqrt(16))  # Utilizând funcția 'sqrt' din modul 'math'
```

O altă construcție utilă este `from module import *`.
`*` înseamnă că toate funcțiile din modul vor fi importate.
Excepție fac funcțiile al căror nume începe cu `_` (underscore).
Acestea sunt considerate "private" și nu vor fi importate folosind `*`, dar vor fi dacă le importăm selectiv sau dacă importăm întregul modul.

Să presupunem că avem urmatorul modul Python, numit `test.py`:

```python
def _private_func():
  print("I am private!")

def public_func():
  print("I am public!")
```

În funcție de cum îl imporăm, vom putea avea sau nu acces la funcția `_private_func()`.

```python
import test

test._private_func()
test.public_func()
# Ambele apeluri se efectuează corect
```

```python
from test import *

public_func()     # Corect
_private_func()   # Incorrect, va rezulta o eroare
```

```python
from test import public_func, _private_func

public_func()
_private_func()
# Ambele apeluri sunt corecte
```

Construcția `from module import *` nu este însă recomandată deoarece poate genera coliziuni de nume între funcții din module diferite, precum în exemplul de mai jos:

```python
# modul a.py
def foo():
  print("I am foo from module a")

# modul b.py
def foo():
  print("I am foo from module b")

# modulul rulat:
from a import *
from b import *

foo()   # Care foo() trebuie rulat?
```

Soluția este să importăm modulul folosind `import module`.
În plus, acest mod de a importa un modul ne permite ușor să schimbă o bibliotecă cu alta (dacă va apărea nevoia aceasta).
Astfel putem diferenția între cele 2 funcții `foo()`:

```python
# modulul rulat:
import a
import b

a.foo()   # Apelăm foo() din modulul a
b.foo()   # Apelăm foo() din modulul b
```

## Aliasuri pentru Module

- **Utilizarea `import module as alias`:** Permite definirea unui alias pentru un modul. Acest lucru este util pentru a scurta numele modulului sau pentru a evita conflictele de nume.

Exemplu de alias pentru modul:

```python
# Importul unui modul cu alias
import math as m

print(m.pi)    # Accesând constanta 'pi' din modulul 'math' folosind aliasul 'm'
```

## Exerciții

1. Creați un modul `formule.py` care să conțină funcții pentru calculul ariei și volumului unui cilindru și ale unei sfere.
Importați doar funcțiile pentru cilindru din modul într-un alt fișier și utilizați-le pentru a calcula aria și volumul unui cilindru cu raza și înălțimea date.

    Rezultat așteptat:
    ```python
    Aria cilindrului cu inaltimea 5 si raza 3 este: 150.79644737231007
    Volumul cilindrului cu inaltimea 5 si raza 3 este: 141.3716694115407
    ```
    Valorile pot diferi la nivelul zecimalelor, din cauza aproximațiilor cu care operează procesorul.

1. Creați un modul numit `util.py` care să conțină o funcție `salut()` și o variabilă `versiune = 1.0`.
Importați modulul utilizând un alias și folosiți funcția și variabila definite în modul cu aliasul creat.
