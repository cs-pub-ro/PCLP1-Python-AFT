---
title: Hello, World
parent: Introducere în limbajul Python
nav_order: 2
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Hello, World
## Cum se execută o comandă în interpretorul Python?

Pentru a executa o comandă în interpretorul Python, deschide terminalul sau linia de comandă și urmează acești pași:

1. **Deschide Terminal:**
   - Pe Windows: Deschide Command Prompt sau PowerShell.
   - Pe macOS și Linux: Deschide Terminal.

2. **Lansează Interpretorul Python:**
   - Scrie `python` sau `python3` și apasă `Enter`. Dacă aceste comenzi nu sunt recunoscute, poate fi necesar să instalezi Python în prealabil și să adaugi calea către executabil în variabila de mediu `PATH`.

3. **Scrie și Execută Comanda Python:**
   - Odată ce te afli în interpretorul Python, poți scrie și executa comenzi Python direct în prompt. De exemplu:

     ```python
     >>> print("Hello, World!")
     ```

     Apasă `Enter` pentru a vedea rezultatul comenzii. În acest exemplu, ar trebui să obții output-ul `"Hello, World!"`.

4. **Ieșire din Interpretor:**
   - Poți ieși din interpretor tastând `exit()` sau `quit()` și apăsând `Enter`.

Observă că simbolurile `>>>` reprezintă promptul interpretorului Python și indică că poți scrie cod Python direct acolo.

Aceasta este modalitatea interactivă de a testa sau de a executa comenzi Python în interpretorul interactiv.
Este util pentru experimentarea rapidă și pentru testarea micilor bucăți de cod.
Pentru proiecte mai mari și scripturi, este obișnuit să scrii codul într-un fișier și să-l rulezi folosind comanda `python nume_script.py` în linia de comandă.

## Cum accesez documentația?

Din consolă puteți obține **documentația** despre anumite module, clase, metode folosind help(nume), inclusiv despre modulele și metodele scrise de voi dacă includeți în cod comentarii [docstring](http://www.python.org/dev/peps/pep-0257/) (similare javadoc-ului din Java).
Alternativ, dacă doriți să vedeți metodele disponibile pentru un anumit obiect puteți folosi funcția `dir(obiect)`, ca în exemplele de [aici](http://www.trytoprogram.com/python-programming/python-built-in-functions/dir/).

```python
>>> import io
>>> help(open)
```

## Validarea rapidă a unei comenzi

Unul din avantajele Python este că puteți folosi consola atunci când vreți să testați o anumită funcționalitate sau când nu sunteți siguri ce se întâmplă când folosiți anumite funcții/construcții.
De exemplu puteți încerca diverse metode de prelucrare pe string-uri înainte de a le încorpora în programul vostru, sau poate pur și simplu vă puneți întrebări de genul "Ce se întâmplă dacă adun două șiruri de caractere (string-uri)? Dar dacă adun un număr cu un string?" –> încercați asta în consolă și observați dacă merge sau ce eroare primiți din partea interpretorului.

## Exerciții

Observați și reproduceți exemplele de mai jos:

```python
>>> "Hello, " + "World!"
'Hello, World!'
```

Ce mesaj transmite eroarea de mai jos?
```python
>>> 2 + "Hello"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

Cum a fost rezolvată problema de mai sus?
```python
>>> str(2) + "Hello"
'2Hello'
```