---
title: Moștenirea
parent: Clase
nav_order: 3
---
<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC 
{:toc}
</details>

Moștenirea în Python este un concept fundamental în programarea orientată pe obiect care permite o clasă să "moștenească" atributele și metodele altei clase. Clasa care moștenește este denumită clasa derivată sau subclasă, iar clasa din care se moștenește este denumită clasă de bază sau clasă părinte.

Iată câteva aspecte cheie ale moștenirii în Python:

1. **Definirea unei Clase Derivate:**
   - Pentru a crea o clasă derivată, specificați clasa părinte între paranteze după numele clasei derivate.

   Exemplu:
   ```python
   class Vehicul:
       def afiseaza_informatii(self):
           print("Acesta este un vehicul.")

   class Masina(Vehicul):  # Masina este o subclasă a Vehicul
       def accelereaza(self):
           print("Mașina accelerează.")
   ```

2. **Accesarea Metodelor Părintelui:**
   - O subclasă poate accesa metodele și atributele clasei părinte folosind funcția `super()`.

   Exemplu:
   ```python
   class Masina(Vehicul):
       def accelereaza(self):
           super().afiseaza_informatii()
           print("Mașina accelerează.")
   ```

    - În constructor clasei copil este necesar să se apeleze constructorul clasei părinte pentru ca copilul, în general, se bazează pe câmpurile din clasa părinte.

3. **Suprascrierea Metodelor:**
   - O subclasă poate suprascrie (override) metodele clasei părinte, oferindu-i o implementare specifică pentru subclasă.

   Exemplu:
   ```python
   class Masina(Vehicul):
       def afiseaza_informatii(self):
           print("Acesta este un tip de vehicul - mașină.")
   ```

4. **Adăugarea de Atribute și Metode Noi:**
   - O subclasă poate adăuga noi atribute și metode specifice acelei subclase.

   Exemplu:
   ```python
   class Masina(Vehicul):
       numar_roti = 4

       def afiseaza_numar_roti(self):
           print(f"Această mașină are {self.numar_roti} roți.")
   ```

5. **Verificarea Tipului de Obiect:**
   - Funcțiile precum `isinstance()` sau `issubclass()` pot fi folosite pentru a verifica tipul de obiect sau relația de moștenire între clase.

   Exemplu:
   ```python
   masina_mea = Masina()
   print(isinstance(masina_mea, Vehicul))  # True
   ```

Moștenirea în Python oferă o modalitate eficientă de reutilizare a codului, promovând modularitatea și extensibilitatea. Cu toate acestea, trebuie utilizată cu grijă pentru a evita dependențele excesive și pentru a menține o structură clară și coerentă a clasei.

## Exerciții


1. **Geometrie Simplă**
   - Creați o clasă de bază `Forma` cu atribute precum `nume` și `culoare`. Definiți o subclasă `Cerc` care să moștenească de la `Forma` și să aibă un atribut suplimentar pentru raza cercului.

2. **Figuri Geometrice Avansate**
   - Extindeți exercițiul cu cercuri adăugând o subclasă `Dreptunghi` care să moștenească de la `Forma` și să aibă atribute suplimentare pentru lungime și lățime.

3. **Gestiunea Angajatilor**
   - Creați o clasă de bază `Angajat` cu atribute precum `nume` și `salariu`. Definiți o subclasă `Manager` care să moștenească de la `Angajat` și să aibă un atribut suplimentar pentru numărul de angajați subordonați.

   - Implementați metoda calculeaza_salariu_total în clasa Manager, care să calculeze salariul total al managerului și al tuturor angajaților subordonați. Adăugați un algoritm care să itereze prin lista de angajați subordonați și să adune salariile lor la salariul total al managerului.

   - Adăugați o clasa `Companie` care are o lista de `Manager`i. Implementati o metodă care să intoarcă suma totală care este platită pentru salarii la nivelul intregii companii.
