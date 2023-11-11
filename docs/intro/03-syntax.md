---
title: Syntax
parent: Introducere în limbajul Python
nav_order: 3
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Particularități de sintaxă

## Indentarea

Atunci când dezvoltăm software în limbajul Python, indentarea este extrem de importantă.

Indentarea reprezintă un aspect esențial al structurii și sintaxei codului.
În Python, indentarea se referă la spațiile sau taburile adăugate în fața liniilor de cod pentru a indica blocurile de cod asociate cu anumite structuri de control, cum ar fi buclele și instrucțiunile condiționale.

Principalele aspecte legate de indentarea în Python includ:

1. **Blocuri de Cod:** În Python, blocurile de cod sunt delimitate de indentare, nu de acolade `{}` (cum ar fi în C sau Java). Acest lucru înseamnă că spațiile sau taburile de la începutul liniilor determină în ce măsură o linie de cod face parte dintr-un anumit bloc.

2. **Consistență:** Este important să păstrezi o indentare consecventă în întregul cod. De obicei, se folosesc 4 spații pentru fiecare nivel de indentare, dar important este să alegi un stil și să-l respecți în tot proiectul.

3. **Structurile de Control:** Indentarea este folosită pentru a indica corpul unei instrucțiuni sau structuri de control, precum buclele `for` și `while`, și instrucțiunile condiționale `if`, `elif`, și `else`.

Exemplu de cod cu indentare corectă în Python:

```python
if x > 0:
    print("x este pozitiv")
    print("Aceasta este o linie din blocul if")
else:
    print("x este negativ sau zero")
    print("Aceasta este o linie din blocul else")
```

Dacă indentarea nu este corectă, poți primi erori de sintaxă sau codul va conține erori de logică.

## Comentariile

Comentariile în limbajul de programare Python sunt porțiuni de text în codul sursă care sunt ignorate de interpretor și nu influențează în niciun fel execuția programului.
Acestea sunt utilizate pentru a explica sau documenta codul, facilitând înțelegerea acestuia pentru alți programatori (sau chiar pentru tine în viitor) și pentru a face observații relevante despre anumite porțiuni de cod.

În Python, există două tipuri principale de comentarii:

1. **Comentarii pe o linie:**
   - Acestea încep cu caracterul `#` și se extind până la sfârșitul liniei.
     Comentariile pe o linie sunt folosite pentru a adăuga explicări sau observații la o linie specifică de cod.

    ```python
    # Aceasta este o comentariu pe o linie
    variabila = 42  # Un alt comentariu pe aceeași linie
    ```

2. **Comentarii pe mai multe linii:**
   - Acestea încep și se termină cu trei ghilimele simple (`'''`) sau cu trei ghilimele duble (`"""`).
     Comentariile pe mai multe linii sunt utile atunci când vrei să adaugi explicații extinse sau documentare la mai multe linii de cod.

    ```python
    '''
    Acesta este un comentariu
    pe mai multe linii
    care explică un bloc de cod.
    '''

    """
    Un alt comentariu
    pe mai multe linii.
    """
    ```
   - Comentariile cu ghilimele succesive din interiorul unui bloc de cod trebuie să fie pe același nivel de indentare cu acesta, altfel interpretorul va genera o eroare de tipul `IndentationError` la execuție.
     Comentariile cu # nu au această restricție

Comentariile sunt esențiale pentru dezvoltarea unui cod bine documentat și ușor de înțeles.
Ele contribuie la claritatea și întreținerea codului, oferind context și explicații pentru diverse aspecte ale programului.
Este recomandat să adaugi comentarii semnificative acolo unde este necesar, dar să eviți adăugarea excesivă de comentarii redundante care pot afecta negativ lizibilitatea codului.

## Coding Style

**Coding style** se referă la regulile și convențiile pe care un programator sau o echipă de programatori le adoptă pentru a formata și organiza codul sursă într-un mod coerent și ușor de înțeles.
Adoptarea unui coding style coerent ajută la menținerea unui standard în cadrul proiectelor software și facilitează colaborarea între membrii echipei.

Un coding style include reguli referitoare la aspecte precum:

1. **Indentarea:** Stabilirea numărului de spații sau taburi folosite pentru a indenta blocurile de cod.

2. **Spațierea:** Definirea spațiilor dintre operatori, variabile și alte elemente ale codului.

3. **Lungimea Liniei de Cod:** Stabilirea unui număr maxim de caractere pe linie, pentru a menține lizibilitatea.

4. **Nomenclatura Variabilelor:** Convenții privind numele variabilelor și ale funcțiilor.

5. **Comentariile:** Cum și când să folosim comentariile în cod pentru a explica porțiuni de cod.

6. **Organizarea Codului:** Cum sunt organizate și grupate funcțiile, clasele, și modulele în cadrul proiectului.

7. **Gestionarea Excepțiilor:** Cum să gestionăm și să notificăm erorile în cod.

Adoptarea unui coding style nu este doar o chestiune estetică; aceasta are un impact semnificativ asupra întreținerii codului, a lizibilității și a consistenței în cadrul unui proiect.
Multe limbaje de programare, inclusiv Python, au recomandări sau standarde oficiale de coding style.
În cazul Python, există [PEP 8](https://peps.python.org/pep-0008/) (Python Enhancement Proposal 8), care furnizează ghiduri și recomandări pentru coding style în limbajul Python.

Adoptarea unui coding style înseamnă că membrii echipei sau programatorii individuali urmează aceleași reguli atunci când scriu cod, ceea ce duce la un cod mai ușor de înțeles, de întreținut și de dezvoltat pe termen lung.