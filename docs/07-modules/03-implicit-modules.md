---
nav_order: 3
tile: Module Implicite în Python
parent: Module în Pyhton
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
