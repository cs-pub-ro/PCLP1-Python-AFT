---
nav_order: 1
title: Crearea și Importarea unui Modul în Python
parent: Module în PyhtonC
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Crearea unui Modul în Python

În Python, crearea și importarea modulelor sunt procese esențiale pentru organizarea și extinderea codului. Aceste acțiuni permit împărțirea codului în unități logice și reutilizabile, facilitând gestionarea și extinderea proiectelor.

## Structura Modulului

**Definirea Funcțiilor și Variabilelor:** Într-un fișier Python separat, definesc funcții, clase, variabile sau alte elemente specifice pe care doriți să le includăți în modulul respectiv.

Exemplu simplu:
```python
# module.py - Exemplu de modul definit
def greet():
    print("Salut din modul!")
```

## Importarea unui Modul în Python

### Utilizarea `import`

- **Importarea Modulului:** Folosiți instrucțiunea `import` pentru a accesa funcțiile, clasele sau variabilele definite în modulul respectiv.
- **Utilizarea Elementelor Modulului:** După importare, puteți folosi elementele modulului prin intermediul numelui modulului și a funcției, clasei sau variabilei specifice.

Exemplu:
```python
# main.py - Fișierul principal care importă modulul definit
import module

module.greet()  # Va afișa "Salut din modul!"
```

### Fișiere Rulate și Importate

Construcția `if __name__ == "__main__"` este folosită în Python pentru a determina dacă fișierul curent este rulat direct ca un script sau este importat ca modul în alt fișier Python.
Acest bloc de cod permite executarea unor instrucțiuni specifice atunci când fișierul este rulat ca script, dar nu când este importat ca modul în alt cod.

Imaginați-vă că aveți un fișier numit `calcule.py` care conține funcții matematice:

```python
# calcule.py

def adunare(a, b):
    return a + b

def scadere(a, b):
    return a - b

if __name__ == "__main__":
    # Exemple de utilizare când fișierul este rulat ca script
    rezultat_adunare = adunare(5, 3)
    print("Rezultat adunare:", rezultat_adunare)

    rezultat_scadere = scadere(10, 4)
    print("Rezultat scadere:", rezultat_scadere)
```

Când rulați `calcule.py` ca un script, blocul `if __name__ == "__main__"` va fi executat. Dar dacă importați acest fișier ca modul în alt fișier Python, acele instrucțiuni din blocul `if __name__ == "__main__"` nu se vor executa. De exemplu:

```python
# alt_fisier.py
import calcule

# Dacă rulăm acest fișier, blocul `if __name__ == "__main__"` din `calcule.py` nu se va executa.
# Putem însă folosi funcțiile definite în `calcule.py` în acest fișier sau în alte module importate.
rezultat_adunare = calcule.adunare(8, 2)
print("Rezultat adunare în alt fișier:", rezultat_adunare)
```

Practic, blocul `if __name__ == "__main__"` oferă o metodă pentru a distinge între rularea directă a unui fișier ca script și importarea sa ca modul în alt cod. Acest lucru este util atunci când dorești să ai anumite instrucțiuni care să se execute doar atunci când rulezi direct acel fișier, dar nu și atunci când îl importezi în altă parte a proiectului tău.

## Exercițiu

1. Creați un modul numit `geometrie.py`.
În acest modul, definiți funcții pentru calculul ariei și perimetrului unui cerc și unui dreptunghi.
Importați și utilizați aceste funcții într-un alt fișier numit `calcul_geometric.py`.
Folosiți `__name__` în ambele fișiere și rulați-le pe amândouă pentru a observa comportamentul.

    Rezultat așteptat:
    ```python
    Aria cercului cu raza 5: 78.53981633974483
    Perimetrul cercului cu raza 5: 31.41592653589793
    Aria dreptunghiului cu lungime 6 si latime 4: 24
    Perimetrul dreptunghiului cu lungime 6 si latime 4: 20
    ```
    Valorile pot diferi la nivelul zecimalelor, din cauza aproximațiilor cu care operează procesorul.
