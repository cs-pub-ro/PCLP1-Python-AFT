---
title: Tipuri de date de bază
parent: Introducere în limbajul Python
nav_order: 4
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Tipuri de date și variabile

## Variabile

O variabilă în programare este un loc de stocare cu un nume simbolic (nume de variabilă) asociat, folosit pentru a reprezenta și stoca date într-un program. Variabilele sunt utilizate pentru a atribui și a memora informații pe care programul le poate manipula. Ele reprezintă concepte fundamentale în majoritatea limbajelor de programare.

Caracteristici ale variabilelor includ:

1. **Nume:** Fiecare variabilă are un nume unic, prin care poate fi referită în cadrul programului. Numele variabilelor trebuie să respecte reguli specifice în funcție de limbajul de programare (de exemplu, să înceapă cu o literă sau un caracter de subliniere în Python).

2. **Tip:** O variabilă are un tip de date care definește tipul de informație pe care îl poate stoca (cum ar fi întregi, reale, șiruri de caractere, etc.). Tipul variabilei determină operațiile care pot fi efectuate asupra ei.

3. **Valoare:** Variabilele pot stoca o valoare specifică asociată cu tipul lor. Această valoare poate fi schimbată în timpul execuției programului.

De exemplu, în Python, poți declara o variabilă numită `x` și îi poți atribui o valoare astfel:

```python
x = 5
```

În acest exemplu, `x` este numele variabilei, iar `5` este valoarea asociată acesteia. După această linie de cod, variabila `x` poate fi utilizată pentru a reprezenta sau a manipula valoarea `5` în cadrul programului.

Utilizarea variabilelor este esențială pentru programare, deoarece oferă un mecanism de lucru cu date și de gestionare a informațiilor în cadrul programelor.

Python oferă tipuri de date numerice, booleene, șiruri (string, liste etc), dicționare, fișiere, clase, instanțe și excepții.

**Important.**
Din punct de vedere al tipării Python folosește tipuri pentru obiecte, însă la definirea variabilelor nu trebuie precizat tipul acestora.
Constrângerile de tip sunt verificate la execuție (late binding), astfel încât pot apărea erori și excepții generate de folosirea unui tip necorespunzător în atribuiri și excepții.

Python asociază numele unei variabile cu un obiect, care poate fi număr, șir de caractere sau ceva mai complex.
Când este folosită o variabilă, tipul acesteia este tipul obiectului cu care este asociată.
Este greșită folosirea într-o expresie a unei variabile care nu a fost asociată cu un obiect.

## Exerciții

Observați și reproduceți exemplele de mai jos în interpretorul Python.

1. Definirea unei variablie

   ```python
   >>> i = 5         # i va fi de tip Integer
   >>> i = "Hello"   # i va fi de tip String
   ```

   Alocarea și dezalocarea de memorie se face automat de către Python, existând un mecanism de garbage collection.

2. În Python se poate face atribuirea de valori unor mai multe variabile simultan:

   ```python
   >>> x, y = 2, 3
   ```

3. Datorită faptului că partea dreaptă a unei expresii este evaluată înainte de a se face atribuirea, valorile a două variabile pot fi foarte ușor interschimbate, fară a avea nevoie de o a treia variabilă:

   ```python
   >>> x, y = y, x
   ```

4. **Important.** Python este un limbaj **dynamically typed**, după cum am arătat și mai sus, dar și **strongly typed**, nepermițând tipului unei variabile să se schimbe atunci când este folosită în operații, decât printr-o conversie explicită.
   De exemplu, codul de mai jos va arunca o excepție la execuție.
   ```python
   >>> '12' + 10
   ```
   Șirul de caractere `'12'` trebuie convertit într-un număr întreg
    ```python
   >>> int('12') + 10
    ```

## Șiruri de caractere

Un șir de caractere, cunoscut și sub numele de "string" în limbajul de programare, reprezintă o secvență de caractere. Un caracter poate fi orice simbol, literă, cifră sau semn de punctuație. Șirurile de caractere sunt folosite pentru a reprezenta text în limbajele de programare.

De obicei, șirurile de caractere sunt delimitate de ghilimele sau apostroafe. De exemplu:

```python
string1 = "Aceasta este o propoziție."
string2 = 'Și aceasta este o altă propoziție.'
```

Stringurile ce conțin mai multe linii sunt înconjurate de trei ghilimele sau apostrofuri succesive """.
```python
s = "string pe o linie"
linie = """string
pe mai multe linii"""
```

Pentru lucrul cu șiruri de caractere, Python oferă tipul String și o serie de operații de bază pe acesta, descrise în [documentație](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str).

### Operatorul de indexare `[]`

În majoritatea limbajelor de programare, caracterele într-un șir sunt indexate începând de la zero. Acest lucru înseamnă că primul caracter al șirului are indexul 0, al doilea are indexul 1, și așa mai departe.

De exemplu:

```python
my_string = "Hello, World!"
print(my_string[0])  # Va afișa primul caracter, adică "H"
print(my_string[7])  # Va afișa caracterul de la poziția 7, adică "W"
```

Stringurile sunt tratate ca niște liste, `cuvant[i]` fiind caracterul din șir ce are indexul `i`, unde `i` ia valori în intervalul `[-length,length)`.
Folosirea unei valori în afara acestui interval va genera o eroare: IndexError: string index out of range.
Python permite și folosirea unor indici negativi, care indexează elementele pornind de la sfârșitul șirului, precum în exemplul de mai jos

```
stringul:         s   t   r   i   n   g
index:            0   1   2   3   4   5
index negativ:   -6  -5  -4  -3  -2  -1 
```

**Încercați** exemplul de mai jos în interpretorul Python:

```python
my_string = "string"
print(my_string[1])  # Va afișa al doilea caracter, adică "t"
print(my_string[-6])  # Va afișa primul caracter, adică "s"
```

**Nu** există un tip de date special pentru caractere, acestea sunt văzute drept șiruri de lungime 1.
Lungimea unui șir se poate afla cu ajutorul funcției: `len(some_string)`.

```python
my_string = "string"
print(len(my_string)) # Va afișa 6
```

### Extragerea unui subșir: operatorul `:`

Caracterul `:` specifică un **subșir** al unui şir folosind sintaxa: `some_string[x:y]`.
Subșirul obținut conține toate caracterele din șirul inițial (some_string) între pozițiile x si y-1 (inclusiv).
Dacă nu se specifică x sau y, acestea au implicit valorile 0, respectiv lungimea șirului.

```python
my_string = "string"
print(my_string[1:3])  # Va afișa "tr"
print(my_string[1:])  # Va afișa "tring"
print(my_string[:3])  # Va afișa "str"
```

### Modificarea unui string

String-urile sunt **immutable**.
Odată create, ele nu mai pot fi modificate.

```python
>>> s = "abcdef"
>>> s[0] = "g"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```

Deși nu pot fi modificate, o variabilă poate referi un string nou creat
```python
>>> s = "abcdef"
>>> s = "g" + s[1:]
>>> print(s) # va afișa "gbcdef"
```

### Alte operații cu șiruri de caractere

Șirurile de caractere pot fi concatenate (adăugate unele la altele) și pot fi supuse diferitelor operații, cum ar fi tăierea (slice) sau căutarea subșirurilor.
   * Pot fi **concatenate** folosind simbolul +
   * Pot fi **multiplicate** folosind caracterul *
   * Se poate folosi operatorul % pentru formatarea șirurilor similar printf-ului din C
   * Modulul [string](http://docs.python.org/3/library/string.html) oferă șiruri predefinite și metoda **format** pentru crearea șirurilor (utilă în special când vrem să incorporăm în șir mai multe variabile).
     Atât la folosirea acestei metode, cât și a operatorului `%` nu este nevoie de conversia explicită la string a variabilelor.
   * Se poate folosi [string interpolation](https://peps.python.org/pep-0498/) (cunoscut și ca **format strings**) ca o alternativă a metodei **format** pentru a folosi numele variabilelor și expresii valide Python în cadrul string-urilor. Un format string începe cu caracterul `f`, astfel `f"acesta este un format string"`.
   ```python
   >>> my_str = "world"
   >>> my_num = 10
   >>> string_interp = f"Hello, {my_str}. The result of the expression 2 * 10 is {2 * my_num}"
   ```
   * Modulul [str](http://docs.python.org/3/library/stdtypes.html#string-methods) oferă metode de lucru cu șirurile precum `index`, `replace`, `split`, `isdigit`, `format` (similar `format`-ului din modulul `string`)

```python
s = "string"          
print(s[0:2])        # st
print(s[:3])         # str
print(s[3:])         # ing
s2 = "one"          
 
print("Write " + 2*s2 + " " + s)                # Write oneone string
print("hello %s, lab %d  !" % ("students",1))   # hello students, lab 1  !             
 
import string
print("hello {}, lab {}".format("world",1))     # hello world, lab 1
print("hello {0}, lab {1}".format("world",1))   # incepand cu python 2.6   

# With string interpolation (also known as)
lab_num = 1
print(f"hello lab {lab_num}")
```

În concluzie, șirurile de caractere sunt componente esențiale ale programelor, utilizate pentru a reprezenta și manipula text într-un mod structurat și eficient.

## Tipuri de date numerice

În Python se poate lucra cu numere întregi și numere în virgulă mobilă.
Numerele întregi dintr-o expresie se convertesc automat în numere în virgulă mobilă dacă este necesar.
Cele patru tipuri numerice int, long, float și complex și operațiile acestora sunt descrise în [documentația oficială](http://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-long-complex).
În afară de operațiile aritmetice standard (`+`, `-`, `*`, `/`), există operatori pentru modulo `%` și pentru ridicarea la putere `**`.

Deoarece Python este **strongly typed**, nu se face conversie automată între tipurile de date dintr-o expresie, cum ar fi operațiile între tipurile String și Integer.
Pentru acest lucru se folosesc funcțiile `int(some_string)` pentru transformarea din string în integer și respectiv `str(some_int)` pentru transformarea din integer în string.

**Atenție!** În cazul transformării din string în integer, dacă stringul ce trebuie convertit conține și alte caractere decât cifre, la execuție va apărea o eroare: `Value Error: invalid literal for int() with base 10.`

```python
print("Un string:", "4" + "2")                 # Un string: 42
print("Un numar:", 4 % 3 + int("41"))          # Un numar: 42
print("Un string:", "4" + str(2))              # Un string: 42
print('persoana %s are %d ani' % ("X", 42))    # persoana X are 42 ani
print((2.0 + 3.0j) * (2.1  -6.0j))             # (22.2-5.7j)
print(2 ** 3 ** 2)                             # 512 
```