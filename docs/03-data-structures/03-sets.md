---
nav-order: 3
title: Seturi
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

# Seturi 

În Python, un set este o colecție neordonată de elemente distincte. Seturile sunt utile atunci când avem nevoie să lucrăm cu mulțimi de date în care ordinea elementelor nu este importantă și nu dorim să avem elemente duplicate.

Principalele caracteristici ale seturilor în Python includ:

1. **Elemente Unice**: Seturile nu permit elementelor duplicate. Dacă încerci să adaugi un element deja existent, setul nu va suferi modificări.

2. **Neordonate**: Elementele dintr-un set nu sunt stocate într-o anumită ordine. Accesul la elemente se face prin intermediul iterației, iar indexarea directă nu este disponibilă.

3. **Mutabile**: Seturile sunt mutabile, ceea ce înseamnă că poți adăuga sau elimina elemente după crearea setului.

## Cum putem crea un set?
Există două modalități principale de a crea un set în Python:
1. Folosind **acolade {}**; Acesta este modul cel mai concis și comun de a crea un set. Pui elementele separate prin virgulă între acolade. Este important să observi că acest mod de a crea un set poate fi confundat cu dicționarele, dar în cazul seturilor, nu avem perechi cheie: valoare, doar elemente: 
```python
set_exemplu = {1, 2, 3, 4, 5}
``` 
2. Folosind **funcția set()**; Poți crea un set folosind **funcția set()** și oferind o altă colecție (cum ar fi o listă) ca argument. **Funcția set()** va elimina duplicatele și va crea un set cu elementele unice rămase.
```python
alt_set = set([3, 4, 5, 6, 7])
```

Ambele metode rezultă în același tip de obiect: un set. În general, folosirea acoladelor **{}** este preferată atunci când creezi un set cu elemente fixe, în timp ce **funcția set()** este utilă atunci când ai deja o altă colecție de elemente din care vrei să creezi un set.

## Cum accesăm elementele unui set?
Elementele dintr-un set nu sunt accesate direct prin index, deoarece seturile sunt neordonate. Cu toate acestea, poți itera prin set pentru a accesa fiecare element. 

```python
set_exemplu = {1, 2, 3, 4, 5}

# Iterare prin set
for element in set_exemplu:
    print(element)
```
Există și metode specifice pe care le poți folosi pentru a verifica dacă un element este prezent într-un set.

```python
set_exemplu = {1, 2, 3, 4, 5}
# Verificare dacă un element este în set
if 3 in set_exemplu:
    print("3 este în set")

# Verificare dacă un element nu este în set
if 6 not in set_exemplu:
    print("6 nu este în set")
```
## Cum aflăm numărul de elemente dintr-un set?
Pentru a afla numărul de elemente dintr-un set în Python, se poate utiliza **funcția len()**. Această funcție returnează lungimea (numărul de elemente) a unei colecții, inclusiv a seturilor.
```python
set_exemplu = {1, 2, 3, 4, 5}

# Află lungimea setului
lungime_set = len(set_exemplu)

print("Numărul de elemente în set este:", lungime_set)
```
## Cum adăugăm elemente într-un set?
Pentru a adăuga elemente într-un set în Python, se utilizează metoda **add()** pentru adăugarea unui singur element sau metoda **update()** pentru adăugarea mai multor elemente într-un singur pas.
```python
set_exemplu = {1, 2, 3}

# Adăugare unui singur element
set_exemplu.add(4)

print(set_exemplu)
# Output: {1, 2, 3, 4}
```

```python
set_exemplu = {1, 2, 3}

# Adăugare mai multe elemente
set_exemplu.update([3, 4, 5])

print(set_exemplu)
# Output: {1, 2, 3, 4, 5}
```
Este important să țineți cont că seturile nu permit elemente duplicate, deci dacă încercați să aduăgați un element care deja există în set, nu se va întâmpla nimic.
## Cum eliminăm elemente dintr-un set?
1.Folosind **metoda remove()**:
```python
set_exemplu = {1, 2, 3, 4, 5}

# Elimină elementul 3 din set
set_exemplu.remove(3)

print(set_exemplu)
# Output: {1, 2, 4, 5}
```
Dacă elementul specificat nu există în set, **metoda remove()** va genera o excepție KeyError. Dacă dorești să eviți această excepție, poți folosi **metoda discard()**.

2. Folosind **metoda discard()**:
```python
set_exemplu = {1, 2, 3, 4, 5}

# Elimină elementul 3 din set (fără excepție dacă nu există)
set_exemplu.discard(3)

print(set_exemplu)
# Output: {1, 2, 4, 5}
```

3. Folosind **metoda pop()**:
```python
set_exemplu = {1, 2, 3, 4, 5}

# Elimină și returnează un element arbitrar din set
element_elim = set_exemplu.pop()

print("Element eliminat:", element_elim)
print(set_exemplu)
# Output: Element eliminat: 1
#         {2, 3, 4, 5}
```
**Metoda pop()** elimină și returnează un element arbitrar din set. Este important să ții cont că, deoarece seturile nu sunt ordonate, nu poți ști exact care element va fi eliminat.

4. Folosind **metoda clear() pentru a șterge toate elementele**:
```python
set_exemplu = {1, 2, 3, 4, 5}

# Șterge toate elementele din set
set_exemplu.clear()

print(set_exemplu)
# Output: set()
```
## Operații pe seturi
1. **Reuniune (Union)** - Creează un set care conține toate elementele din ambele seturi.
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
reuniune = set1.union(set2)
print(reuniune)
# Output: {1, 2, 3, 4, 5}
```
2. **Intersecție (Intersection)** - Creează un set care conține doar elementele comune din ambele seturi.
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
intersectie = set1.intersection(set2)
print(intersectie)
# Output: {3}
```
3. **Diferență (Difference)** - Creează un set care conține elementele din primul set care nu sunt prezente în al doilea set.
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
diferenta = set1.difference(set2)
print(diferenta)
# Output: {1, 2}
```
4. **Diferență simetrică (Symmetric Difference)** - Creează un set care conține elementele care sunt prezente într-unul dintre seturi, dar nu în ambele.
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
diferenta_simetrica = set1.symmetric_difference(set2)
print(diferenta_simetrica)
# Output: {1, 2, 4, 5}
```
5. **Subset** și **Superset** - Verifică dacă un set este submulțime sau supramulțime al altui set.
```python
set1 = {1, 2, 3, 4, 5}
set2 = {2, 3}
is_subset = set2.issubset(set1)
is_superset = set1.issuperset(set2)
print(is_subset)  # Output: True
print(is_superset)  # Output: True
``` 
## Cum copiem un set?
Pentru a copia elementele dintr-un set în altul în Python, poți folosi metoda **copy()** sau poți crea un set nou folosind constructorul **set()**.
1. Folosind **copy()**:
```python
set1 = {1, 2, 3}
set2 = set1.copy()
print(set2)
# Output: {1, 2, 3}
```
2. Folosind **set()**:
```python
set1 = {1, 2, 3}
set2 = set(set1)
print(set2)
# Output: {1, 2, 3}
```
Atât **copy()** cât și **set()** vor crea o copie a setului inițial. Dacă faci modificări într-un set, aceste modificări nu vor afecta celălalt set, deoarece copiile sunt independente.

### De ce nu folosim operatorul **=** când vrem să copiem elementele dintr-un set în alt set?

Folosirea operatorului **=** pentru a atribui un set unui alt set creează o referință către același obiect **set** în memorie, nu o copie separată a setului. Acest lucru înseamnă că modificările făcute într-un set vor afecta și celălalt set. Iată un exemplu care arată acest comportament:
```python
set_original = {1, 2, 3, 4, 5}

# Atribuire folosind =
set_copie = set_original

# Modifică setul original
set_original.add(6)

print("Set original:", set_original)
# Output: Set original: {1, 2, 3, 4, 5, 6}

print("Copie set:", set_copie)
# Output: Copie set: {1, 2, 3, 4, 5, 6}
```

## Cum putem face un set imutabil?

În Python, seturile în mod implicit sunt mutabile, ceea ce înseamnă că pot fi modificate prin adăugarea, eliminarea sau actualizarea elementelor. Dacă dorești să creezi un set imutabil, poți folosi tipul de date **frozenset**.

Un **frozenset** este o versiune imutabilă a unui set. După ce a fost creat, nu poți adăuga, elimina sau actualiza elemente într-un **frozenset**.
```python
# Crearea unui frozenset imutabil
set_imutabil = frozenset([1, 2, 3, 4, 5])

# Încercare de adăugare a unui element (va genera o eroare)
set_imutabil.add(6) # va da eroare

# Încercare de eliminare a unui element (va genera o eroare)
set_imutabil.remove(3) # va da eroare

print("Set imutabil:", set_imutabil)
# Output: Set imutabil: frozenset({1, 2, 3, 4, 5})
```
