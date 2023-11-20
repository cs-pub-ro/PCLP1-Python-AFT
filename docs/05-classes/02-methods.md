---
title: Metode
parent: Clase
nav_order: 2
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Metode

## Atribute ale claselor vs. Atribute ale instațelor

Diferența principală dintre atributele claselor și atributele instanțelor în Python constă în modul în care sunt stocate și utilizate.

1. **Atributele Claselor:**
   - Atributele claselor sunt definite la nivelul clasei și nu depind de o instanță specifică a clasei.
   - Acestea sunt partajate între toate instanțele aceleiași clase.
   - Pot fi accesate folosind numele clasei sau orice instanță a acelei clase.

   Exemplu:
   ```python
   class Masina:
       numar_masini = 0  # Atribut de clasă

       def __init__(self, marca, model):
           self.marca = marca  # Atribut de instanță
           self.model = model  # Atribut de instanță
           Masina.numar_masini += 1  # Accesare atribut de clasă și modificare
   ```

2. **Atributele Instanțelor:**
   - Atributele instanțelor sunt specifice unei instanțe particulare a unei clase.
   - Acestea sunt definite în interiorul metodei `__init__` sau pot fi adăugate la o instanță oricând după crearea ei.
   - Fiecare instanță a clasei poate avea valori diferite pentru aceleași atribute.

   Exemplu:
   ```python
   class Masina:
       def __init__(self, marca, model):
           self.marca = marca  # Atribut de instanță
           self.model = model  # Atribut de instanță
   ```

Pe scurt, atributele claselor sunt compartimentate la nivel de clasă și sunt comune tuturor instanțelor acelei clase, în timp ce atributele instanțelor sunt specifice fiecărei instanțe și pot avea valori diferite pentru fiecare obiect creat din clasă. Atributele claselor sunt utile atunci când doriți să partajați o valoare între toate instanțele unei clase sau să mențineți un contor comun, în timp ce atributele instanțelor sunt folosite pentru a stoca date specifice unei instanțe individuale.

## Tipuri de metode

Metodele claselor în Python sunt funcții definite în interiorul unei clase și sunt utilizate pentru a îndeplini operații specifice pe obiecte create din acea clasă. Există mai multe tipuri de metode într-o clasă, iar două dintre cele mai comune sunt:

1. **Metode de instanță (`self`):**
   - Acestea sunt metode care operează asupra instanțelor specifice ale clasei.
   - Primele parametre ale acestor metode trebuie să fie `self`, care reprezintă instanța obiectului curent.
   - Aceste metode pot accesa și modifica atributele instanței.

   Exemplu:
   ```python
   class Masina:
       def __init__(self, marca, model):
           self.marca = marca
           self.model = model

       def afiseaza_informatii(self):
           print(f"Mașina {self.marca} {self.model}")
   ```

   În acest exemplu, `afiseaza_informatii` este o metodă de instanță care accesează atributele instanței (`self.marca` și `self.model`).

2. **Metode de clasă (`cls`):**
   - Acestea sunt metode care operează asupra întregii clase, nu doar asupra instanțelor.
   - Primul parametru al acestor metode este, de obicei, denumit `cls` și reprezintă clasa însăși.
   - Aceste metode pot accesa și modifica atributele claselor, dar nu pot accesa direct atributele instanțelor.

   Exemplu:
   ```python
   class Masina:
       numar_masini = 0

       def __init__(self, marca, model):
           self.marca = marca
           self.model = model
           Masina.numar_masini += 1

       @classmethod
       def afiseaza_numar_masini(cls):
           print(f"Număr total de mașini: {cls.numar_masini}")
   ```

   În acest exemplu, `afiseaza_numar_masini` este o metodă de clasă care accesează atributul clasei `numar_masini`.

Acestea sunt tipurile principale de metode într-o clasă, dar există și alte tipuri, precum:

- **Metode statice:** Acestea sunt metode care nu accesează nici atributele instanței, nici cele ale clasei. Ele sunt definite cu decoratorul `@staticmethod`.

  Exemplu:
  ```python
  class Calculator:
      @staticmethod
      def aduna(a, b):
          return a + b
  ```

## Exerciții

1. **Creați o clasă pentru un Calculator:**
   - Definiți o clasă `Calculator` care să aibă metode pentru adunare, scădere, înmulțire și împărțire. Testați clasa cu diverse operații. Operatiile se fac pe cate 2 operanzi.

2. **Creați o clasă pentru un Student:**
   - Definiți o clasă `Student` cu atribute precum nume, vârstă și note. Adăugați o metodă care să calculeze media notelor. Creați câteva instanțe de student și afișați informațiile.

3. **Creați o clasă pentru un Cerc:**
   - Definiți o clasă `Cerc` cu un atribut pentru raza și metode pentru calcularea circumferinței și a ariei. Testați clasa cu diferite valori de rază.

4. **Creați o clasă pentru un Rezervor de Apă:**
   - Definiți o clasă `RezervorApa` cu un atribut pentru cantitatea de apă și metode pentru adăugarea și scoaterea apei. Asigurați-vă că cantitatea de apă rămâne întotdeauna pozitivă.

5. **Gestiunea Angajatilor:**
   - Creați o clasă pentru un Angajat, cu atribute precum nume, salariu și departament. Adăugați o metodă pentru creșterea salariului. Creați apoi o listă de angajați și afișați informațiile lor.
