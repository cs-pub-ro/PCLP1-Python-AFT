---
nav-order: 1
title: Liste
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

# Liste

În Python, o listă este o structură de date care permite stocarea și manipularea unui set de elemente într-o secvență ordonată. Listele sunt definite prin utilizarea parantezelor drepte **[]** sau folosind **list()**. 

Listele sunt folosite într-o varietate de situații pentru stocarea și manipularea datelor, de la colectarea informațiilor la implementarea algoritmilor și structurilor de date mai complexe. De asemenea, listele sunt utile atunci când avem date care își schimbă valoarea frecvent în timpul execuției unui program.

## Definirea unei liste
```python
lst = []
lst = [1, 2, 3]

lst = list()
lst = list((1, 2, 3))
```

## Caracteristicile principale ale unei liste

<ol>
<li> <b>Ordonare</b>: Elementele listei sunt stocate într-o ordine specifică și pot fi accesate prin intermediul unui index.
<li> <b>Mutabilitate</b>: Listele sunt mutabile, ceea ce înseamnă că poți adăuga, elimina sau modifica elemente după ce lista a fost creată.
<li> <b>Diversitate de elemente</b>: O listă poate conține elemente de diferite tipuri, inclusiv alte liste. Așa că spunem despre o listă că este <b>eterogenă</b>.
<li> <b>Elemente duplicate</b>: O listă poate conține două sau mai multe elemente care au aceeași valoare.
<li> <b>Metode încorporate</b>: Python oferă numeroase metode încorporate pentru lucrul cu liste, pe care le vom discuta mai mult în continuare.
</ol>

## Verificarea existenței unui element într-o listă
```python
lst = [3, 2, 1, 9]
2 in lst
```

## Cum accesăm elementele unei liste?

Elementele unei liste pot fi accesate folosind **indici** sau conceptul de **slicing**, util atunci când vrem să accesăm numai o sublistă din lista inițială.

### Accesare folosind indici
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst[1] # vom accesa astfel al doilea element din lista noastră.
lst[-1] # vom accesa astfel ultimul element din lista noastră.
lst[-2] # vom accesa astfel penultimul element din lista noastră.
```

### Accesare folosind slicing
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst[1:3] # vom accesa astfel al doilea și al treilea element din lista noastră.
lst[0:5:2] # vom accesa astfel primul, al treilea și al cincilea element din lista noastră.
```

## Cum aflăm lungimea unei liste?

Pentru a face acest lucru putem folosi **len()**.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
len(lst) # rezultatul acestui apel va fi 6
```

## Cum parcurgem o listă?

### Folosind un for loop (for-each)
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
for elem in lst:
    print(elem) # vom afișa fiecare element din listă
```

### Folosind un indice
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
for i in range(0, len(lst)):
    print(lst[i]) # vom afișa fiecare element din listă
```

## Operații utile pe liste

### Adăugarea unui element in listă
Pentru a adăuga un element într-o listă pot fi folosite metode specifice listelor precum **append()**, **insert()** și **extend()**.

Metoda **append()** poate primi un singur parametru, iar acel parametru va fi adăugat la finalul listei.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.append(10) # lst va fi [1, 2, "Ion", 4, 7, [2, 3, "Maria"], 10]
lst.append([6, 7]) # lst va fi [1, 2, "Ion", 4, 7, [2, 3, "Maria"], 10, [6, 7]]
```

Metoda **insert()** în Python este folosită pentru a adăuga un element la o anumită poziție (index) într-o listă. Această metodă modifică lista originală și deplasează elementele ulterioare pentru a face loc noului element.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.insert(2, 3) # lst va fi [1, 2, 3, "Ion", 4, 7, [2, 3, "Maria"]]
```

Metoda **extend()** în Python este utilizată pentru a extinde o listă prin adăugarea tuturor elementelor dintr-o altă colecție (cum ar fi o listă, un tuplu, un set, un șir). Această metodă modifică lista originală.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.extend([2, 3]) # lst va fi [1, 2, "Ion", 4, 7, [2, 3, "Maria"], 2, 3]
```

### Modificarea elementelor unei liste

O listă în Python este o secvență mutabilă de obiecte iterabile, astfel permițând modificarea elementelor sale. Modificările pot fi realizate folosind numărul de **index** și **operatorul de atribuire (=)** pentru a asigna o valoare nouă unui element.

Iată o descriere pentru cele două scenarii de modificare posibile:

1. **Modificarea unui singur element**: Pentru a modifica un element specific dintr-o listă, se utilizează indexul acestuia împreună cu operatorul de atribuire.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst[0] = -1 # lst va fi [-1, 2, "Ion", 4, 7, [2, 3, "Maria"], 2, 3]
```
2. **Modificarea unui interval de elemente**: Pentru a modifica un interval de elemente dintr-o listă, se poate folosi slicing-ul și operatorul de atribuire. 
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst[0:2] = [3, 4] # lst va fi [3, 4, "Ion", 4, 7, [2, 3, "Maria"]]
```

3. **Modificarea tuturor elementelor**: Pentru a modifica toate elementele folosim un for loop.
```python
lst = [1, 2, 3]
for i in range(0, len(lst)):
    square = lst[i] * lst[i]
    lst[i] = square
```

### Ștergerea elementelor dintr-o listă

Elementele unei liste pot fi eliminate din listă folosind următoarele metode:

1. **remove(element)**: Pentru a elimina prima apariție a elementului din listă.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.remove(2) # lst va fi [2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.remove(9) # acest apel va da eroare pentru că 9 nu se află în listă
```
2. **pop(index)**: Elimină și returnează elementul de la indexul dat din listă.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.pop(1) # lst va fi [1, "Ion", 4, 7, [2, 3, "Maria"]]
x = lst.pop(1) # x va fi "Ion", iar lst va fi lst = [1, 4, 7, [2, 3, "Maria"]]
lst.pop() # lst va fi [1, 4, 7]
```
3. **clear()**: Pentru a elimina toate elementele din listă. Rezultatul va fi o listă goală.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
lst.clear() # lst va fi [] - lista vidă
```
4. **del nume_listă**: Șterge întreaga listă.
```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
del lst[1] # lst va fi [1, "Ion", 4, 7, [2, 3, "Maria]]
del lst # apelul va șterge lst și tot ce conține aceasta
print(lst) # va da eroare pentru că lst nu mai există
```

### Găsirea unui element în listă

Pentru a găsi un element într-o listă se folosește metoda **index()**. Funcția **index()** va accepta valoarea elementului ca parametru și va returna poziția primei apariții a elementului în listă. Dacă elementul nu există în listă metoda va întoarce o eroare.

```python
lst = [1, 2, "Ion", 4, 7, [2, 3, "Maria"]]
x = lst.index(4) # x va fi 3
```

### Concatenarea a două liste

Concatenarea a două liste înseamnă îmbinarea lor într-o singură listă. Există două moduri de a face acest lucru:

1. Folosind operatorul **+**. 
```python
lst1 = [1, 2, 3]
lst2 = [4, 5, 6]
lst_rez = lst1 + lst2 # lst_rez va fi [1, 2, 3, 4, 5, 6]
```
2. Folosind metoda **extend()**. Metoda **extend()** adaugă elementele listei noi la sfârșitul listei la care este aplicată.
```python
lst1 = [1, 2, 3]
lst2 = [4, 5, 6]
lst1.extend(lst2) # lst1 va fi [1, 2, 3, 4, 5, 6]
```

### Copierea unei liste

Există două moduri prin care se poate crea o copie a unei liste:

1. Folosind **operatorul de atribuire (=)**: Noua listă va fi un **deep copy**. Modificările pe care le facem în lista originală se vor reflecta și în noua listă.
```python
lst1 = [1, 2, 3]
lst2 = lst1
lst1.append(4)
print(lst1) # lst1 va fi [1, 2, 3, 4]
print(lst2) # lst2 va fi [1, 2, 3, 4]
```

2. Folosind **metoda copy()**. Aceasta va crea o listă nouă și orice modificări făcute în lista originală nu se vor reflecta în lista nouă. Acest lucru se numește **shallow copy**.
```python
lst1 = [1, 2, 3]
lst2 = lst1.copy()
lst1.append(4)
print(lst1) # lst1 va fi [1, 2, 3, 4]
print(lst2) # lst2 va fi [1, 2, 3]
```

### Sortarea unei liste

Funcția **sort()** sortează elementele din listă în ordine crescătoare.
```python
lst = [4, 1, 2, 7, 3, 6]
lst.sort() # lst va fi [1, 2, 3, 4, 6, 7]
```

### Inversarea unei liste

Funcția **reverse()** este folosită pentru a inversa ordinea elementelor dintr-o listă.
```python
lst = [1, 5, 6, 3]
lst.reverse() # lst va fi [3, 6, 5, 1]
```

## Funcții built-in Python ce operează pe liste

### Sum
```python
lst = [1, -1, 3, 2]
sum(lst) # rezultatul va fi 5
```

### Min și Max
```python
lst = [1, -1, 3, 2]
max(lst) # rezultatul va fi 3
min(lst) # rezultatul va fi -1
```
