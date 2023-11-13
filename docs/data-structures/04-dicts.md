---
nav-order: 4
title: Dicționare
parent: Data Structures
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Dicționare

Dicționarele în Python sunt structuri de date care stochează perechi cheie-valoare. Acestea sunt utile pentru a organiza și accesa date într-un mod eficient. Într-un dicționar, fiecare cheie trebuie să fie unică și asociată cu o valoare specifică. Cheile pot fi de diferite tipuri de date (șiruri, numere, tupluri), în timp ce valorile pot fi orice tip de date. Exemplu:

```python
student = {
    'nume': 'Ana',
    'varsta': 25,
    'nota': 9.5
}
```

În acest exemplu, 'nume', 'varsta', și 'nota' sunt chei, iar 'Ana', 25, și 9.5 sunt valorile corespunzătoare.

Dicționarele sunt utile în Python din mai multe motive:

1. Acces rapid la date: Dicționarele permit accesul rapid la date utilizând chei unice. Acest lucru face că căutarea unui element să fie eficientă și rapidă.

2. Structură cheie-valoare: Dicționarele oferă o modalitate flexibilă de a organiza datele sub forma unor perechi cheie-valoare. Aceasta face gestionarea și manipularea datelor mult mai ușoară.

3. Diversitate în tipurile de chei și valori: Cheile și valorile din dicționare pot fi de orice tip de date. Aceasta oferă o flexibilitate semnificativă în gestionarea diferitelor tipuri de informații.

4. Modificabile: Dicționarele sunt structuri de date mutable, ceea ce înseamnă că poți adăuga, modifica și șterge elemente după ce dicționarul a fost creat.

5. Utilizare în probleme de mapare: Dicționarele sunt adesea utilizate pentru a rezolva probleme de mapare, unde o cheie este asociată cu o valoare specifică.

6. Eficiență în căutare: Dicționarele sunt implementate intern cu o structură de date numită "tabel de dispersie" (hash table), ceea ce face ca operațiile de căutare să fie eficiente, cu o complexitate medie O(1).

7. Extensibilitate și flexibilitate: Dicționarele oferă o structură extensibilă și flexibilă pentru organizarea și manipularea datelor. Poți include liste, alte dicționare sau orice alt tip de date ca valori într-un dicționar.

Pentru a ilustra, să luăm un exemplu simplu:

```python
student = {
    'nume': 'Ana',
    'varsta': 25,
    'materii': ['Matematică', 'Fizică', 'Chimie'],
    'note': {'Matematică': 9, 'Fizică': 8, 'Chimie': 9.5}
}

```

În acest exemplu, putem accesa rapid informații despre student utilizând chei specifice, cum ar fi student['materii'] pentru a obține lista materiilor sau student['note']['Matematică'] pentru a obține nota la Matematică.

## Cum putem crea un dicționar?

Există mai multe moduri de a crea un dicționar:

1. Folosind **acoladele (curly brackets)**: 
```python
student = {} # dicționar vid
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}
```
2. Folosind constructorul **dict()**:
```python
student = dict() # dicționar vid
student = dict(nume='Ana', varsta=25, nota=9.5)
```
3. Folosind o **secvență (un tuplu) cu fiecare element ca o pereche (cheie-valoare)**:
```python
perechi = [('nume', 'Ana'), ('varsta', 25), ('nota', 9.5)]
student = dict(perechi)
```
4. Folosind **metoda fromkeys()**:
```python
chei = ['nume', 'varsta', 'nota']
valori = ['Ana', 25, 9.5]
student = dict.fromkeys(chei, valori)
```

## Cum putem accesa elementele unui dicționar?
Accesarea elementelor unui dicționar în Python se face prin specificarea cheii asociate elementului respectiv. Iată câteva modalități de a accesa elemente într-un dicționar:

1. Prin **specificarea cheii**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Accesarea valorii prin specificarea cheii
nume_student = student['nume']
varsta_student = student['varsta']
nota_student = student['nota']

print(nume_student)  # Output: Ana
print(varsta_student)  # Output: 25
print(nota_student)  # Output: 9.5
```

2. Folosind **metoda get()**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Accesarea valorii folosind metoda get()
nume_student = student.get('nume')
varsta_student = student.get('varsta')
nota_student = student.get('nota')

print(nume_student)  # Output: Ana
print(varsta_student)  # Output: 25
print(nota_student)  # Output: 9.5
```
Avantajul metodei **get()** este că nu generează o eroare dacă cheia nu există, returnând None în schimb.

## Cum parcurgem un dicționar?
1. Iterarea **prin chei**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

for cheie in student:
    print(cheie, ':', student[cheie])
```
2. Iterarea prin **metoda keys()**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

for cheie in student.keys():
    print(cheie, ':', student[cheie])
```
3. Iterarea **prin valori**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

for valoare in student.values():
    print(valoare)
```
4. Iterarea **prin perechi cheie-valoare folosind metoda items()**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

for cheie, valoare in student.items():
    print(cheie, ':', valoare)
```

## Cum aflăm lungimea unui dicționar?
Pentru a afla lungimea (numărul de elemente) a unui dicționar în Python, puteți utiliza funcția **len()**.
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

lungime_dictionar = len(student)

print(f'Lungimea dicționarului este: {lungime_dictionar}')
```
În acest exemplu, len(student) returnează numărul de chei din dicționarul student, ceea ce înseamnă lungimea dicționarului.


## Cum adăugăm / actualizăm elemente într-un dicționar?

1. Adăugare/Actualizare **prin specificarea cheii**:
```python
student = {'nume': 'Ana', 'varsta': 25}

# Adăugare/actualizare a unei noi informații
student['nota'] = 9.5
```
2. Folosind **metoda update()**:
```python
student = {'nume': 'Ana', 'varsta': 25}

# Adăugare a unei noi perechi cheie-valoare sau actualizare dacă cheia există deja
student.update({'nota': 9.5, 'sex': 'feminin'})
```
3. Folosind **metoda setdefault()**:
```python
student = {'nume': 'Ana', 'varsta': 25}

# Adăugare a unei noi perechi cheie-valoare doar dacă cheia nu există deja
student.setdefault('nota', 9.5)
```
4. Folosind **metoda dict.fromkeys()**:
```python
chei = ['nume', 'varsta', 'nota']
valoare_implicita = 0

# Creare dicționar folosind o listă de chei și o valoare implicită
student = dict.fromkeys(chei, valoare_implicita)
```
După ce ați adăugat elementele dorite, dicționarul va arăta în mod corespunzător. Este important să rețineți că metodele precum **update()** vor actualiza valorile dacă cheile deja există, în timp ce **metoda setdefault()** sau **adăugarea directă prin specificarea cheii** vor adăuga doar dacă cheia nu există încă în dicționar.

## Cum ștergem elemente dintr-un dicționar?
1. Ștergerea **prin specificarea cheii folosind del**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Ștergerea cheii 'nota' și a valorii asociate
del student['nota']
```
2.Folosind **metoda pop()**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Ștergerea cheii 'nota' și returnarea valorii asociate
nota = student.pop('nota')
```
3. Folosind **metoda popitem()**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Ștergerea ultimei perechi cheie-valoare adăugate și returnarea acesteia
ultima_pereche = student.popitem()
```
4. Folosind **metoda clear()**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Ștergerea tuturor elementelor din dicționar
student.clear()
```
5. Folosind **del pentru ștergerea întregului dicționar**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Ștergerea întregului dicționar
del student
```
Este important să alegeți metoda potrivită în funcție de ce doriți să realizați. De exemplu, **del** și **pop** sunt mai potrivite atunci când știți cheia pe care doriți să o ștergeți, în timp ce **popitem** este mai potrivită dacă doriți să ștergeți ultima pereche cheie-valoare adăugată. **clear** este folosit pentru ștergerea tuturor elementelor din dicționar, iar **del** pentru ștergerea întregului dicționar.
## Cum verificăm existența unei chei / unei valori într-un dicționar?
1. Verificarea **existenței cheii cu in**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Verificarea existenței cheii 'nota'
if 'nota' in student: # echivalent cu if 'nota' in student.keys():
    print("Cheia 'nota' există în dicționar.")
```
2. Verificarea **existenței unei valori cu in**:
```python
student = {'nume': 'Ana', 'varsta': 25, 'nota': 9.5}

# Verificarea existenței valorii 25
if 25 in student.values():
    print("Valoarea 25 există în dicționar.")
``` 
## Cum unim două dicționare?
Unirea a două dicționare în Python se poate realiza folosind **metoda update()**. Această metodă adaugă perechile cheie-valoare dintr-un alt dicționar în dicționarul curent. Dacă există chei comune, valorile vor fi actualizate cu cele din dicționarul furnizat.
```python
dicționar1 = {'nume': 'Ana', 'varsta': 25}
dicționar2 = {'nota': 9.5, 'oră': '12:00'}

# Unirea dicționarelor
dicționar1.update(dicționar2)

# Afișarea rezultatului
print(dicționar1)
```
În acest exemplu, dicționar1 va fi actualizat cu perechile cheie-valoare din dicționar2. Dacă există chei comune, valorile din dicționar1 vor fi înlocuite cu cele din dicționar2.

Dacă doriți să creați un dicționar nou fără a le modifica pe cele existente, puteți folosi operatorul de despărțire **{\*\*dicționar1, \*\*dicționar2}**. Aceasta este o metodă disponibilă în Python 3.5 și versiunile ulterioare:
```python
dicționar1 = {'nume': 'Ana', 'varsta': 25}
dicționar2 = {'nota': 9.5, 'oră': '12:00'}

# Crearea unui nou dicționar prin unire
nou_dicționar = {**dicționar1, **dicționar2}

# Afișarea rezultatului
print(nou_dicționar)
```

## Cum copiem un dicționar?

Există mai multe moduri de a copia un dicționar în Python. Importante sunt două tipuri de copii: copiere profundă (deep copy) și copiere superficială (shallow copy).

1. **Copiere superficială**:
    - Se poate realiza folosind **metoda copy()** sau operatorul de atribuire **(=)**.
    - Într-o copie superficială, obiectele încorporate (cum ar fi listele sau alte dicționare) nu sunt copiate, ci doar referințele către acestea.
    ```python
    # Folosind copy()
    dicționar1 = {'cheie': 'valoare', 'lista': [1, 2, 3]}
    copie_superficiala = dicționar1.copy()

    # Folosind operatorul de atribuire
    altă_copie_superficială = dicționar1.copy()

    # Modificarea copiei superficiale nu afectează dicționarul original
    copie_superficiala['cheie'] = 'noua_valoare'
    copie_superficiala['lista'][0] = 99

    print(dicționar1)  # {'cheie': 'valoare', 'lista': [99, 2, 3]}
    ```
2. **Copiere profundă**:
    - Se poate realiza folosind modulul copy și funcția deepcopy().
    - Într-o copie profundă, toate obiectele încorporate sunt, de asemenea, copiate în mod recursiv.
    ```python
    from copy import deepcopy

    dicționar1 = {'cheie': 'valoare', 'lista': [1, 2, 3]}
    copie_adâncime = deepcopy(dicționar1)

    # Modificarea copiei adâncime nu afectează dicționarul original
    copie_adâncime['cheie'] = 'noua_valoare'
    copie_adâncime['lista'][0] = 99

    print(dicționar1)  # {'cheie': 'valoare', 'lista': [1, 2, 3]}
    ```
Dacă obiectele încorporate în dicționar sunt mutable și doriți să evitați modificările reflectate între original și copie, este recomandat să utilizați **deepcopy()** pentru a obține o copie profundă. Pentru obiecte imutabile, cum ar fi numerele sau șirurile, copierea superficială poate fi suficientă.
