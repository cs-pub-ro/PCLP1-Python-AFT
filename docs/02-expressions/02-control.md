---
title: Instrucțiuni de control
parent: Expresii și instrucțiuni de control
nav_order: 2
---

# Instrucțiuni de control

Instrucțiunile de control, cunoscute și sub numele de instrucțiuni de flux de control, sunt construcții de programare care permit programatorului să controleze ordinea de execuție a instrucțiunilor într-un program.
Aceste instrucțiuni determină fluxul programului în funcție de anumite condiții sau bucle.
Cele mai comune tipuri de instrucțiuni de control includ:

1. **Instrucțiuni condiționale (`if`, `else`, `elif`):**
   - Aceste instrucțiuni permit programului să execute diferite blocuri de cod în funcție de condiții specificate.

   ```python
   x = 10
   if x > 0:
       print("x este pozitiv")
   elif x == 0:
       print("x este zero")
   else:
       print("x este negativ")
   ```

2. **Instrucțiuni de buclă (`for`, `while`):**
   - Aceste instrucțiuni permit programului să repete un bloc de cod de mai multe ori.

   ```python
   # Utilizarea unei bucle for
   for i in range(5):
       print(i)  # Afișează numerele de la 0 la 4

   # Utilizarea unei bucle while
   count = 0
   while count < 5:
       print(count)  # Afișează numerele de la 0 la 4
       count += 1
   ```

3. **Instrucțiuni de salt (`break`, `continue`, `pass`):**
   - `break`: Termină prematur bucla.
   - `continue`: Sare peste restul buclei și trece la următoarea iterație.
   - `pass`: Folosit ca marcator când o instrucțiune este necesară din punct de vedere sintactic, dar nu este necesară nicio acțiune.

   ```python
   for i in range(10):
       if i == 5:
           break  # Iese din buclă când i este 5
       print(i)
   ```

4. **Gestionarea Excepțiilor (`try`, `except`, `finally`):**
   - Aceste instrucțiuni sunt folosite pentru a gestiona excepțiile (erorile) care pot apărea în timpul execuției unui program.

   ```python
   try:
       rezultat = 10 / 0
   except ZeroDivisionError:
       print("Nu se poate împărți la zero")
   finally:
       print("Acest bloc se execută întotdeauna")
   ```

Instrucțiunile de control sunt esențiale pentru crearea unor programe flexibile și dinamice care răspund la diferite scenarii.
Ele permit programatorului să dirijeze fluxul de execuție, să gestioneze erori și să implementeze procese iterative.
Utilizarea adecvată a acestor instrucțiuni este crucială pentru scrierea unui cod eficient și ușor de citit.