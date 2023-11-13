---
nav-order: 1
title: Funcții în limbajul Python
parent: Funcții
---

# Funcții în limbajul Python

În Python, o funcție este un bloc de cod reutilizabil, proiectat pentru a efectua o anumită sarcină sau un set de sarcini. Funcțiile sunt definite utilizând cuvântul cheie **def**, urmat de numele funcției și o secțiune de corp a funcției, unde sunt scrise instrucțiunile efective.

## Tipuri de funcții
În Python, există două tipuri de funcții:

1. **Funcții Built-in**: Acestea sunt funcții încorporate în limbajul Python și sunt disponibile pentru utilizare fără a fi necesară definirea lor. Exemple includ **print()**, **len()**, **type()**.
2. **Funcții definite de utilizator**: Acestea sunt funcții create de programatori pentru a-și organiza și structura codul. Definirea unei funcții utilizator se realizează cu ajutorul cuvântului cheie **def**.
    ```python
    def hello_world():
        print("Hello, world!")
    ``` 
## Cum creăm o funcție?
O formă generală a definirii funcțiilor în Python este:
```python
def nume_functie(parametri):
    # Corpul funcției
    # Instrucțiuni
    return rezultat
```

Iată un exemplu simplu de funcție care adună două numere:
```python
def adunare(a, b):
    suma = a + b
    return suma
```
Explicații:

- **def** este cuvântul cheie care indică că începeți să definiți o funcție.
adunare este numele funcției.
- **(a, b)** sunt parametrii funcției. Aceștia sunt valorile pe care funcția le primește pentru a le utiliza în interior.
- **Corpul funcției** este indentat sub definiția funcției și conține operațiile pe care doriți să le efectuați.
- **return** este cuvântul cheie folosit pentru a returna rezultatul funcției.

## Cum apelăm o funcție?
Pentru a apela o funcție în Python, trebuie să utilizați numele funcției, urmat de paranteze care conțin argumentele (dacă funcția acceptă argumente). Iată o sintaxă generală:
```python
rezultat = nume_functie(arg1, arg2, ...)
```
Exemplu:
```python
def adunare(a, b):
    suma = a + b
    return suma

rezultat = adunare(3, 4)
print(rezultat)  # Va afișa: 7
```
În acest exemplu, funcția **adunare** este apelată cu argumentele 3 și 4. Rezultatul returnat de funcție este stocat în variabila rezultat și apoi afișat.

## Cum returnăm o valoare dintr-o funcție?
În Python, folosim instrucțiunea **return** pentru a returna o valoare dintr-o funcție. O funcție poate avea sau nu o instrucțiune **return**, iar dacă are, poate returna o valoare sau mai multe. Iată un exemplu simplu:
```python
def adunare(a, b):
    suma = a + b
    return suma

rezultat = adunare(3, 5)
print("Rezultatul adunării este:", rezultat)
```
În acest exemplu, funcția adunare primește doi parametri, a și b, le adună și apoi returnează rezultatul. Apoi, apelăm funcția cu argumentele 3 și 5, iar rezultatul este stocat în variabila rezultat. În cele din urmă, afișăm rezultatul cu ajutorul instrucțiunii print.

Rețineți că o funcție poate returna orice tip de valoare, inclusiv tipuri de date complexe precum liste, dicționare sau chiar alte funcții.

### Returnarea mai multor valori dintr-o funcție
În Python, poți returna mai multe valori dintr-o funcție folosind un tuplu, listă sau alt tip de structură de date. Iată un exemplu:
```python
def operatii_matematice(a, b):
    suma = a + b
    diferenta = a - b
    produs = a * b
    cat = a / b
    return suma, diferenta, produs, cat

rezultate = operatii_matematice(8, 4)
print("Suma:", rezultate[0])
print("Diferența:", rezultate[1])
print("Produs:", rezultate[2])
print("Cât:", rezultate[3])
```
În acest exemplu, funcția **operatii_matematice** primește doi parametri, a și b, realizează diverse operații matematice și returnează rezultatele sub formă de tuplu. Apoi, atunci când apelăm funcția și primim rezultatul în variabila **rezultate**, putem accesa fiecare valoare din tuplu folosind indexul corespunzător.

Alternativ, poți returna valorile sub formă de listă sau chiar de dicționar, în funcție de necesitățile tale.

## Instrucțiunea **pass**
În Python, instrucțiunea **pass** este folosită ca o instrucțiune vidă. Ea nu face nimic și servește doar pentru a evita erorile de sintaxă atunci când un corp de cod este necesar, dar nu dorești să implementezi nimic în acel moment. De exemplu, într-o funcție, poți folosi pass pentru a indica că funcția este goală și urmează să fie implementată ulterior:
```python
def functie_neimplementata():
    pass
```
Acesta este util în situații în care ai nevoie să păstrezi o structură de cod validă, dar încă nu ai implementat logica specifică funcției.
## Cum sunt executate funcțiile în Python?
În Python, funcțiile permit programatorului să creeze cod scurt și curat, care poate fi reutilizat în întregul program.

Funcțiile ne ajută să organizăm codul. O funcție primește parametri ca intrare, îi procesează și, în final, returnează valori ca rezultat.

Să presupunem că am definit o funcție care efectuează o anumită sarcină. Atunci când apelăm acea funcție dintr-o altă funcție, controlul programului trece la acea funcție, realizează unele calcule și returnează o valoare către funcția apelantă.
## Vizibilitatea variabilelor
În Python, vizibilitatea variabilelor în funcție depinde de unde au fost definite acele variabile. Există câteva reguli de bază:

1. **Variabilele locale**: O variabilă definită într-o funcție este locală și este vizibilă doar în interiorul acelei funcții. Ea există doar atât timp cât funcția este în curs de execuție.
    ```python
    def exemplu():
        variabila_locala = 10
        print(variabila_locala)

    exemplu()
    ```
    În acest exemplu, **variabila_locala** este vizibilă doar în interiorul funcției **exemplu()**.

2. **Variabilele globale**: O variabilă definită în afara oricărei funcții sau într-un modul este globală și poate fi accesată din orice loc din program. Cu toate acestea, o funcție nu poate modifica direct o variabilă globală decât dacă este declarată ca globală în interiorul funcției.
    ```python
    variabila_globala = 20

    def exemplu():
        print(variabila_globala)

    exemplu()
    ``` 
În acest exemplu, **variabila_globala** este o variabilă globală și poate fi accesată în interiorul funcției **exemplu()**.

### Cuvântul Cheie global

În Python, cuvântul cheie **global** este folosit pentru a declara o variabilă ca fiind globală într-o funcție. Acest lucru înseamnă că variabila poate fi accesată și modificată atât în interiorul funcției, cât și în afara ei, în cadrul programului.

Atunci când o variabilă este atribuită în interiorul unei funcții fără a utiliza cuvântul cheie **global**, Python creează o nouă variabilă locală în cadrul acelei funcții, care suprascrie variabila globală dacă există una cu același nume.

Utilizarea **global** permite funcției să știe că vrea să lucreze cu variabila globală, nu să creeze o variabilă locală nouă.

Exemplu:
```python
variabila_globala = 10

def modificare_variabila():
    global variabila_globala
    variabila_globala = 20

modificare_variabila()
print(variabila_globala)
```
În acest exemplu, **global variabila_globala** indică faptul că funcția intenționează să lucreze cu variabila globală, nu să creeze o variabilă locală cu același nume. Astfel, după apelul funcției, valoarea variabilei globale este modificată și afișată ca 20.
## Parametrii unei funcții
În Python, parametrii unei funcții pot fi de mai multe tipuri, inclusiv parametri poziționali, parametri cu cuvinte cheie (keyword), parametri cu valori implicite (default), și parametri cu lungime variabilă. Iată o prezentare succintă a fiecărui tip:

1. **Parametrii poziționali**:
    - Acești parametri sunt specificați în ordinea în care sunt așteptați de către funcție.
    - Valorile lor sunt atribuite în ordine, începând cu primul parametru al funcției.
        ```python
        def exemplu_parametri_poziționali(a, b, c):
            # a, b, și c sunt parametri poziționali
            print(a, b, c)

        exemplu_parametri_poziționali(1, 2, 3)  # Va afișa: 1 2 3
        ``` 
    2. **Parametri cu cuvinte cheie (Keyword)**:
    - Valorile sunt asociate explicit cu numele parametrilor.
    - Aceasta oferă flexibilitate în privința ordinii.
        ```python
        def exemplu_parametri_keyword(x, y, z):
            # x, y, și z sunt parametri cu cuvinte cheie
            print(x, y, z)

        exemplu_parametri_keyword(y=2, z=3, x=1)  # Poziția nu mai contează, va afișa: 1 2 3
        ```
3. **Parametri cu valori implicite (Default)**:
    - Acești parametri au valori implicite, astfel încât nu este obligatoriu să li se furnizeze o valoare la apelarea funcției.
        ```python
        def exemplu_parametri_default(a, b=2, c=3):
            # b și c au valori implicite
            print(a, b, c)

        exemplu_parametri_default(1)  # Va afișa: 1 2 3
        ```
4. **Parametri cu lungime variabilă**:
    - Acești parametri permit unei funcții să primească un număr variabil de argumente.
    - Există două tipuri: *args pentru parametrii poziționali și **kwargs pentru parametrii cu cuvinte cheie.
        ```python
        def exemplu_lungime_variabila(arg1, *args, **kwargs):
            print(arg1)
            print(args)    # Tuplu cu argumente poziționale suplimentare
            print(kwargs)   # Dicționar cu argumente cu cuvinte cheie suplimentare

        exemplu_lungime_variabila(1, 2, 3, a=4, b=5)
        # Va afișa:
        # 1
        # (2, 3)
        # {'a': 4, 'b': 5}
        ```
## Funcții recursive
Funcțiile recursive sunt funcții care se apelează pe ele însele în cadrul propriului lor corp. Această tehnică este adesea folosită pentru a rezolva probleme care pot fi împărțite în subprobleme mai mici. În Python, o funcție poate apela orice altă funcție, inclusiv pe ea însăși.

Un exemplu clasic de funcție recursivă este calculul factorialului. Iată un exemplu:

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n - 1)

result = factorial(5)
print(result)  # Va afișa: 120
```

Explicație:

1. Funcția **factorial** primește un argument **n**.
2. În cazul de bază, când **n** este 0 sau 1, se returnează 1 (factorialul lui 0 și 1 este 1).
3. În caz contrar, funcția se apelează recursiv cu argumentul **n - 1** și rezultatul este înmulțit cu **n**.

Deși funcțiile recursive pot oferi o soluție elegantă pentru anumite probleme, este important să se evite recursivitatea nesfârșită. Pentru aceasta, asigurați-vă că există o condiție de oprire bine definită și că aceasta este atinsă în cele din urmă.

De asemenea, trebuie să fiți conștient de consumul de memorie, deoarece fiecare apel recursiv adaugă un cadru nou pe stivă de apeluri, iar stiva poate să crească până la atingerea limitelor de adâncime a stivei de apeluri.

## (Opțional) Docstrings

Docstrings (documentații de șiruri) în Python sunt șiruri de documentație încorporate direct în codul sursă al unui modul, funcție, clasă sau metoda. Acestea sunt folosite pentru a descrie scopul, comportamentul și utilizarea unei componente specifice de cod și oferă un mod eficient de a furniza documentație în interiorul codului.

Docstrings pot fi definite pe o singură linie sau pe mai multe linii. Iată exemple pentru ambele:

1. **Docstrings pe o singură linie**:
    ```python
    def my_function(arg1, arg2):
        """Descrierea funcției."""
        # corpul funcției
        pass
    ```
2. **Docstrings pe mai multe linii:**
    ```python
    def my_function(arg1, arg2):
        """
        Descrierea funcției.

        Args:
        arg1 (tip): Descrierea argumentului 1.
        arg2 (tip): Descrierea argumentului 2.

        Returns:
        tipul_returnat: Descrierea valorii returnate.
        """
        # corpul funcției
        pass
    ```

Este important să menționați că docstrings sunt opționale, dar sunt considerate o practică bună pentru a face codul mai ușor de înțeles și pentru a furniza informații utile altor programatori sau chiar pentru voi înșivă. Puteți accesa docstrings-ul unei funcții sau obiect folosind atributul **\_\_doc\_\_**:
```python
print(my_function.__doc__)
```
Este recomandat să utilizați docstrings și să le mențineți actualizate pe măsură ce evoluează codul.
