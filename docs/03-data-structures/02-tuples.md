---
nav-order: 2
title: Tupluri
parent: Structuri de date
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Tupluri

În Python, un tuplu este o colecție ordonată de elemente, similară cu o listă. Cu toate acestea, există câteva diferențe cheie între liste și tupluri:

1. **Imutabilitate**: Tuplurile sunt imutabile, ceea ce înseamnă că, odată ce un tuplu este creat, nu îl poți modifica adăugând, ștergând sau modificând elementele sale. În schimb, trebuie să creezi un tuplu nou.
2. **Sintaxă**: Tuplurile sunt definite utilizând paranteze rotunde ().

## Cum putem crea un tuplu?
1. Utilizând **paranteze rotunde ()**:
```python
tuplu_vid = ()  # Tuplu vid
tuplu_simplu = (1, 2, 3)
tuplu_mixt = (1, 'doi', 3.0)
```
2. **Fără a folosi paranteze (packing)**:
```python
tuplu_packing = 1, 2, 3
```
În acest caz, Python va crea implicit un tuplu.

3. Utilizând **constructorul tuple()**:
```python
tuplu_constructor = tuple([1, 2, 3])
```
Poți utiliza **tuple()** pentru a converti o altă colecție (cum ar fi o listă) într-un tuplu.

Tuplurile pot conține orice tip de obiecte și pot fi de lungime fixă sau variabilă.

## Cum aflăm numărul de elemente ale unui tuplu?
Pentru a afla numărul de elemente dintr-un set în Python, se poate utiliza **funcția len()**.
```python
tuplu_exemplu = (1, 'doi', 3.0)
lungime_tuplu = len(tuplu_exemplu)

print(lungime_tuplu)  # Output: 3
```
## Cum parcurgem un tuplu?
1. Folosind **bucla for direct**:
    ```python
    tuplu_exemplu = (1, 'doi', 3.0)

    for element in tuplu_exemplu:
        print(element)
    ```
2. Utilizând **funcția enumerate() pentru a obține și indicele**:
    ```python
    tuplu_exemplu = (1, 'doi', 3.0)

    for index, element in enumerate(tuplu_exemplu):
        print(f"Index: {index}, Element: {element}")
    ```
3. Utilizând **un indice într-o buclă for**:
    ```python
    tuplu_exemplu = (1, 'doi', 3.0)

    for index in range(len(tuplu_exemplu)):
        print(tuplu_exemplu[index])
    ```
4. **Despachetând elementele direct**:
    ```python
    tuplu_exemplu = (1, 'doi', 3.0)

    element1, element2, element3 = tuplu_exemplu
    print(element1)
    print(element2)
    print(element3)
    ```
## Cum accesăm elementele dintr-un tuplu?
Elementele dintr-un tuplu pot fi accesate utilizând indexarea. Indexul începe de la 0 pentru primul element și continuă în ordine crescătoare. De asemenea, poți utiliza indexare negativă pentru a accesa elementele în ordine inversă, începând cu -1 pentru ultimul element.
```python
tuplu_exemplu = (1, 'doi', 3.0)

# Accesarea elementului de la indexul 0
primul_element = tuplu_exemplu[0]
print(primul_element)  # Output: 1

# Accesarea elementului de la indexul 1
al_doilea_element = tuplu_exemplu[1]
print(al_doilea_element)  # Output: 'doi'

# Accesarea elementului de la indexul -1 (ultimul element)
ultimul_element = tuplu_exemplu[-1]
print(ultimul_element)  # Output: 3.0
```
## Cum găsim un element într-un tuplu?
Pentru a căuta un anumit element într-un tuplu în Python, poți utiliza metoda **index()**. Această metodă returnează poziția primului element găsit în tuplu.

Metoda **index()** acceptă următoarele trei argumente:

- **item** – Elementul care trebuie căutat în tuplu.
- **start** – (Opțional) Valoarea de început a indexului de la care începe căutarea.
- **end** – (Opțional) Valoarea de sfârșit a căutării indexului.
```python
tuplu_exemplu = (1, 'doi', 3.0, 'doi', 5)

# Cautarea pozitiei elementului 'doi'
pozitie = tuplu_exemplu.index('doi')
print(f"Pozitia elementului 'doi' este: {pozitie}")
```
## Cum adăugăm sau modificăm elemente dintr-un tuplu?
O metodă de a adăuga sau modifica elemente într-un tuplu este să îl converti temporar într-o listă, să efectuezi modificările și apoi să convertești înapoi într-un tuplu.
 
1. **Adăugarea unui element la sfârșitul unui tuplu**:
    ```python
    tuplu_initial = (1, 2, 3)
    element_nou = 4

    # Convertirea tuplului în listă
    lista_temporara = list(tuplu_initial)
    # Adăugarea elementului la listă
    lista_temporara.append(element_nou)
    # Convertirea listei înapoi în tuplu
    tuplu_nou = tuple(lista_temporara)

    print(tuplu_nou)
    # Output: (1, 2, 3, 4) 
    ```
2. **Modificarea unui element într-un tuplu**:
    ```python
    tuplu_initial = (1, 2, 3)
    element_modificat = 10

    # Convertirea tuplului în listă
    lista_temporara = list(tuplu_initial)
    # Modificarea elementului în listă
    lista_temporara[0] = element_modificat
    # Convertirea listei înapoi în tuplu
    tuplu_nou = tuple(lista_temporara)

    print(tuplu_nou)
    # Output: (10, 2, 3)
    ```
## Cum ștergem elemente dintr-un tuplu?
Tuplurile fiind structuri de date imutabile în Python, nu poți șterge direct un element dintr-un tuplu existent. Poți utiliza același principiu de a converti tuplul într-o listă, să ștergi elementul și apoi să convertești lista înapoi într-un tuplu.
```python
tuplu_initial = (1, 2, 3, 4, 5)
element_de_sters = 3

# Convertirea tuplului în listă
lista_temporara = list(tuplu_initial)
# Ștergerea elementului din listă
lista_temporara.remove(element_de_sters)
# Convertirea listei înapoi în tuplu
tuplu_nou = tuple(lista_temporara)

print(tuplu_nou)
# Output: (1, 2, 4, 5)
```
## Cum concatenăm două tupluri?
Concatenarea a două sau mai multe tupluri în Python poate fi realizată în diferite moduri. Un lucru de notat este că tuplurile permit duplicarea, deci dacă două tupluri au același element, acesta va fi repetat de două ori în tuplul rezultat.

1. Utilizând operatorul **+**:
    ```python
    tuplu1 = (1, 2, 3, 4, 5)
    tuplu2 = (3, 4, 5, 6, 7)

    # Concatenare tuple folosind operatorul +
    tuplu3 = tuplu1 + tuplu2
    print(tuplu3)
    # Output (1, 2, 3, 4, 5, 3, 4, 5, 6, 7)
    ```
2. Utilizând **funcția sum()**:
    ```python
    tuplu1 = (1, 2, 3, 4, 5)
    tuplu2 = (3, 4, 5, 6, 7)

    # Folosirea funcției sum
    tuplu3 = sum((tuplu1, tuplu2), ())
    print(tuplu3)
    # Output (1, 2, 3, 4, 5, 3, 4, 5, 6, 7)
    ```
3. Utilizând **funcția itertools.chain()**:
    ```python
    import itertools

    tuplu1 = (1, 2, 3, 4, 5)
    tuplu2 = (3, 4, 5, 6, 7)

    # Folosirea itertools
    tuplu3 = tuple(item for item in itertools.chain(tuplu1, tuplu2))
    print(tuplu3)
    # Output (1, 2, 3, 4, 5, 3, 4, 5, 6, 7)
    ```
## Cum copiem un tuplu?
Pentru a copia elementele dintr-un tuplu în altul, se poate folosi constructorul **tuple()**:
```python
# Tuplul original
tuplu_original = (1, 2, 3, 4, 5)

# Crearea unui tuplu nou prin concatenare
tuplu_copie = tuple(tuplu_original)
print(tuplu_copie)
# Output (1, 2, 3, 4, 5)
```
