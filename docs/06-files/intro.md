---
nav_order: 1
title: Lucrul cu Fișiere în Python
has_children: false
---

# Curs Introductiv: Lucrul cu Fișiere în Python

## 1. Deschiderea și Închiderea Fișierelor

### 1.1 Deschiderea unui Fișier

În Python, utilizăm funcția `open()` pentru a deschide un fișier. Această funcție returnează un obiect de tip fișier

```python
# Deschiderea unui fișier în modul de citire
file = open('nume_fisier.txt', 'r')

# Deschiderea unui fișier în modul de scriere (crearea unui fișier nou sau ștergerea conținutului existent)
file = open('nume_fisier.txt', 'w')

# Deschiderea unui fișier în modul de adăugare (se adaugă la sfârșitul existentului sau se creează un fișier nou)
file = open('nume_fisier.txt', 'a')
```

### 1.2 Închiderea unui Fișier

Este important să închidem un fișier după ce am terminat de lucrat cu el pentru a elibera resursele.

```python
file.close()
```

## 2. Citirea și Scrierea în Fișiere

### 2.1 Citirea din Fișiere

Există mai multe metode pentru a citi conținutul unui fișier:

- `read()`: Citeste întregul conținut al fișierului.
- `readline()`: Citeste o linie din fișier.
- `readlines()`: Citeste toate liniile din fișier și le returnează sub formă de listă.

Exemplu:

```python
file =  open('nume_fisier.txt', 'r')
content = file.read()
print(content)
```

### 2.2 Scrierea în Fișiere

Utilizăm metoda `write()` pentru a scrie într-un fișier.

```python
file = open('nume_fisier.txt', 'w')
file.write('Acesta este un text de exemplu.\n')
file.write('O nouă linie în fișier.')
```

## 3. Gestionarea Blocurilor cu `with`

Utilizarea instrucțiunii `with` este recomandată pentru gestionarea resurselor și a blocurilor de cod.

```python
with open('nume_fisier.txt', 'r') as file:
    content = file.read()
# Lucrăm cu conținutul fișierului aici
# Fișierul se închide automat după blocul `with`
```

Este recomandată folosirea operatorului `with` întrucât acesta gestioneaza in mod automat lucrul cu fisiere.
În cazul în care apar excepții în utilizarea fisierului, `with` se ocupă de eliberareaza resurselor.

## 4. Lucrul cu Linii și Listă de Linii

### 4.1 Iterarea prin Linii

```python
with open('nume_fisier.txt', 'r') as file:
    for line in file:
        print(line)
```

### 4.2 Salvarea Liniilor într-o Listă

```python
with open('nume_fisier.txt', 'r') as file:
    lines = file.readlines()
    for line in lines:
        print(line)
```

## 5. Manipularea Poziției Cursorului

Pentru a seta sau a afla poziția cursorului în fișier, se folosește metoda `seek()`.

```python
with open('nume_fisier.txt', 'r') as file:
    file.seek(10)  # Setează cursorul la byte-ul 10
    content = file.read()
    print(content)
```

## Exerciții

### Analiza unui Fișier CSV

Creați un program care să citească un fișier CSV cu informații despre studenți (nume, notă) și să calculeze media notelor. Salvați rezultatul într-un alt fișier.

```python
# Exemplu de structură CSV: "Nume,Nota"
# Alice,8
# Bob,9
# ...
```

### Combinarea Fișierelor

Creați un program care să combine conținutul mai multor fișiere text într-un singur fișier.

```python
# Exemplu de utilizare:
combina_fisiere(['fisier1.txt', 'fisier2.txt', 'fisier3.txt'], 'rezultat_combinat.txt')
```

### Găsirea Cuvintelor Unice

Creați un program care citește un fișier de text și identifică toate cuvintele unice, ignorând literele mari/mici și semnele de punctuație.

```python
# Exemplu de utilizare:
rezultat = cuvinte_unice('text.txt')
print("Cuvinte Unice:", rezultat)
```

Înțeles, să simplificăm puțin. Iată câteva exerciții mai accesibile:

### Căutare și Înlocuire

Creați un program care citește un fișier de text și permite utilizatorului să introducă un cuvânt pentru căutare și un cuvânt pentru înlocuire. Apoi, înlocuiți toate aparițiile cuvântului de căutare cu cuvântul de înlocuire și salvați noul conținut într-un alt fișier.

```python
# Exemplu de utilizare:
cautare_inlocuire('text.txt', 'text_modificat.txt', 'python', 'programming')
```

### Adăugare Linii

Creați un program care citește un fișier de text și adaugă o linie specificată la începutul sau sfârșitul fișierului

```python
# Exemplu de utilizare:
adauga_linie('text.txt', 'text_modificat.txt', 'Aceasta este o linie adaugata la inceput.', la_inceput=True)
```
