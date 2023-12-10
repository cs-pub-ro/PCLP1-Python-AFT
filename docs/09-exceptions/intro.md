---
nav_order: 9
title: Tratarea erorilor
has_children: true
---

# Tratarea erorilor

## Ce sunt erorile și excepțiile?

În programare, erorile și excepțiile sunt situații care pot apărea în timpul execuției unui program și care pot afecta fluxul normal al acestuia.

In mod normal, erorile reprezinta situatii in care integritatea programului a fost compromisa irecuperabil, astfel incat executia acestuia este oprita.

Exceptiile pe de alta parte, reprezinta situatii in care integritatea programului a fost compromisa, insa se pot luat actiuni pentru a continua executia.

Gestionarea eficientă a erorilor este esențială pentru a asigura robustețea și fiabilitatea programelor.
Un cod care gestionează corect erorile este mai ușor de întreținut și de depanat, iar aplicațiile cu gestionare adecvată a erorilor oferă o experiență mai bună utilizatorilor.

---

## Tipuri de Erori în Python

### Erori de sintaxă
Erorile de sintaxă apar atunci când codul sursă nu respectă regulile de sintaxă ale limbajului Python. Aceste erori sunt detectate în timpul analizei sintactice a codului și trebuie corectate înainte de a rula programul.

```python
if x == 5
    print("x este egal cu 5")
```

### Erori de execuție

Erorile de execuție apar în timpul rulării programului și pot include probleme precum impartirea la zero, accesarea unui indice inexistent într-o listă sau folosirea unui tip de date incorect.

La nivelul limbajului Python nu exista notiunea de exceptie, ci doar erori.
Cu toate acestea, toate erorile (mai putin cele de sintaxa) pot fi tratate.
In consecinta, erorile ce pot fi tratate sunt numite prin conventie exceptii.

```python
# impartire la 0
result = 10 / 0

# accesarea unui index invalid
my_list = [1, 2, 3]
element = my_list[10]

# operatie pe tipuri invalide
result = "10" + 5
```

Pentru fiecare dintre situatiile de mai sus, interpretorul python va arunca o eroare specifica care identifica tipul de eroare.
Ierarhia completa a tipurilor de erori poate fi consultata [aici](https://docs.python.org/3/library/exceptions.html#exception-hierarchy).

## Blocuri Try-Except

### Utilizarea blocurilor try și except
Blocurile `try` și `except` permit gestionarea excepțiilor într-un mod controlat. Codul din blocul `try` este testat pentru excepții, iar în cazul apariției acestora, se execută blocul `except` corespunzător.

### Structura generală a blocurilor try și except
```python
try:
    # Some Code.... 

except:
    # optional block
    # Handling of exception (if required)

else:
    # execute if no exception

finally:
    # Some code .....(always executed)
```

Mai jos aveti un exemplu apropiat de realitate pentru utilizarea exceptiilor:

```python
try:
    # Deschiderea unui fișier în modul citire
    with open("exemplu.txt", "r") as file:
        # Citirea conținutului fișierului
        content = file.read()
    # Tentativa de conversie la întreg a conținutului citit
    number = int(content)
except FileNotFoundError:
    # Excepție pentru cazul în care fișierul nu a fost găsit
    print("Fișierul nu a fost găsit.")
except ValueError:
    # Excepție pentru cazul în care conținutul fișierului nu poate fi convertit la întreg
    print("Conținutul fișierului nu poate fi convertit la întreg.")
else:
    # Blocul else este executat doar dacă nu apare nicio excepție
    print("Conținutul citit din fișier:", content)
    print("Conținutul convertit la întreg:", number)
finally:
    # Blocul finally este întotdeauna executat, indiferent de apariția sau nu a excepțiilor
    print("Închiderea fișierului.")
```

Explicații:
- Încercăm să deschidem fișierul "exemplu.txt" în modul citire (`"r"`).
- Dacă fișierul nu poate fi găsit (`FileNotFoundError`), afișăm un mesaj corespunzător.
- Încercăm să citim conținutul fișierului și să îl convertim la un întreg.
- Dacă conținutul nu poate fi convertit la un întreg (`ValueError`), afișăm un mesaj corespunzător.
- Dacă totul decurge fără erori, blocul `else` este executat și afișează conținutul citit și conținutul convertit.
- Blocul `finally` se ocupă de închiderea fișierului indiferent de rezultat.

Aceasta este o utilizare comună a blocurilor `try`, `except`, `else`, și `finally` pentru gestionarea excepțiilor și resurselor în Python.

## Lansarea Excepțiilor

### Cum să lansați propriile excepții

În Python, poți să arunci manual o excepție folosind cuvântul cheie `raise`. Acesta poate fi folosit pentru a crea și a lansa excepții personalizate în anumite condiții. Iată cum poți face acest lucru:

```python
def verificare_numar_pozitiv(numar):
    if numar <= 0:
        raise ValueError("Numărul trebuie să fie un număr pozitiv.")

# Exemplu de apel al funcției cu un număr pozitiv
try:
    numar_utilizator = int(input("Introduceți un număr pozitiv: "))
    verificare_numar_pozitiv(numar_utilizator)
    print("Numărul introdus este valid.")
except ValueError as ex:
    print(f"Erroare: {ex}")
```

Explicații:

1. **Funcția `verificare_numar_pozitiv`:**
   - Această funcție primește un argument `numar` și verifică dacă este mai mic sau egal cu zero.
   - Dacă condiția nu este îndeplinită, funcția lansează o excepție `ValueError` cu un mesaj asociat.

2. **Blocul `try`:**
   - Încercăm să obținem un număr de la utilizator și apoi apelăm funcția `verificare_numar_pozitiv` pentru a verifica dacă este un număr pozitiv.
   - Dacă funcția găsește o problemă (de exemplu, numărul introdus este negativ sau zero), va lansa o excepție `ValueError`.

3. **Blocul `except`:**
   - Dacă o excepție de tip `ValueError` este prinsă, afișăm un mesaj de eroare corespunzător.

Dacă introduci un număr negativ sau zero la solicitarea de la utilizator, funcția `verificare_numar_pozitiv` va lansa o excepție, iar blocul `except` va prinde această excepție și va afișa un mesaj de eroare. Este o modalitate utilă de a gestiona condițiile de eroare specifice la care programul trebuie să răspundă.

### Crearea și utilizarea propriilor clase de excepții

Crearea și utilizarea unei excepții personalizate în Python implică definirea unei noi clase de excepție care moștenește de la clasa de bază `Exception`. Vom explora această idee printr-un exemplu în care vom crea o excepție personalizată pentru a trata cazul în care un utilizator încearcă să introducă un număr mai mic decât 18 pentru a accesa un anumit conținut destinat doar persoanelor majore.

```python
# Definirea unei excepții personalizate
class VarstaInferioaraError(Exception):
    def __init__(self, mesaj="Trebuie să ai cel puțin 18 ani pentru a accesa acest conținut."):
        self.mesaj = mesaj
        super().__init__(self.mesaj)

# Utilizarea excepției personalizate într-o funcție
def acceseaza_continut(varsta_utilizator):
    if varsta_utilizator < 18:
        raise VarstaInferioaraError()

# Exemplu de utilizare a excepției personalizate într-un bloc try-except
try:
    varsta = int(input("Introduceți vârsta dvs.: "))
    acceseaza_continut(varsta)
    print("Acces permis. Continuăm cu afișarea conținutului.")
except VarstaInferioaraError as ex:
    print(f"Eroare: {ex}")
```

Explicații:

1. **Definirea Excepției Personalizate (`VarstaInferioaraError`):**
   - Se creează o clasă `VarstaInferioaraError` care moștenește de la clasa de bază `Exception`.
   - Constructorul clasei poate primi un mesaj personalizat, dar are și un mesaj implicit în cazul în care nu este furnizat un mesaj.

2. **Utilizarea Excepției Personalizate în Funcția `acceseaza_continut`:**
   - Funcția `acceseaza_continut` primește vârsta utilizatorului și verifică dacă este mai mică decât 18.
   - Dacă este mai mică, funcția aruncă o instanță a excepției personalizate `VarstaInferioaraError`.

3. **Blocul `try-except`:**
   - În blocul `try`, citim vârsta utilizatorului și apelăm funcția `acceseaza_continut`.
   - Dacă funcția aruncă o excepție de tipul `VarstaInferioaraError`, blocul `except` prinde această excepție și afișează un mesaj de eroare.

4. **Exemplu de Utilizare:**
   - Utilizatorul este solicitat să introducă vârsta.
   - Dacă vârsta introdusă este mai mică decât 18, funcția `acceseaza_continut` va arunca o excepție `VarstaInferioaraError` și va fi afișat un mesaj de eroare corespunzător.

Crearea excepțiilor personalizate oferă posibilitatea de a gestiona situații specifice într-un mod clar și coerent. Puteți personaliza excepțiile pentru a se potrivi nevoilor specifice ale aplicației sau bibliotecii dvs.


### Exerciții practice


#### Divizor neegal

Scrieți o funcție numită `divizor_neegal` care primește doi parametri, `numar` și `divizor`. Funcția trebuie să împartă `numar` la `divizor` și să returneze rezultatul împărțirii. Cu toate acestea, funcția trebuie să gestioneze situația în care `divizor` este 0 prin aruncarea unei excepții personalizate numite `DivizorZeroError`.

Scrieți, de asemenea, un bloc try-except în afara funcției pentru a apela funcția cu diferite valori ale divizor, inclusiv 0, și pentru a afișa un mesaj corespunzător în cazul apariției excepției `DivizorZeroError`.

#### Verificare parola

Scrieți o funcție numită `verifica_parola` care primește o parolă ca argument și efectuează următoarele verificări:

1. Parola trebuie să aibă cel puțin 8 caractere.
1. Parola trebuie să conțină cel puțin o literă majusculă și o literă minusculă.
1. Parola trebuie să conțină cel puțin un caracter special (de exemplu, !, @, #, $, %).
1. Dacă una dintre aceste condiții nu este îndeplinită, funcția ar trebui să arunce o excepție personalizată numită ParolaInvalidaError cu un mesaj corespunzător.

Scrieți un bloc try-except în afara funcției pentru a apela funcția verifica_parola cu diferite parole și pentru a afișa un mesaj corespunzător în cazul apariției excepției ParolaInvalidaError.

#### Gestionare Cont Bancar cu Excepții

1. Definiți o clasă SoldInsuficientError care să moștenească de la clasa de bază Exception. Această clasă va fi folosită pentru a semnala că o tranzacție nu poate fi efectuată din cauza fondurilor insuficiente în cont.

1. Definiți clasa ContBancar cu următoarele metode:

- __init__(self, nume, sold_initial): Inițializează un cont bancar cu un nume și un sold_initial.
- depune(self, suma): Adaugă suma specificată la soldul contului.
- extrage(self, suma): Extrage suma specificată din soldul contului. Dacă suma este mai mare decât soldul, aruncă o excepție SoldInsuficientError.
- afiseaza_sold(self): Afișează soldul curent al contului.

În blocul try-except, creați o instanță a clasei ContBancar și efectuați câteva tranzacții, cum ar fi depuneri și extrageri. Gestionarea erorilor ar trebui să includă tratarea excepției SoldInsuficientError și afișarea unui mesaj de eroare corespunzător.
