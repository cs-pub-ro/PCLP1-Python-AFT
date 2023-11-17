---
title: Metode de baza
parent: Clase
nav_order: 1
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Metode de baza

## `__init__`

Metoda `__init__` este un constructor special în Python și este folosită pentru a inițializa obiectele create dintr-o clasă.
Este apelată automat atunci când se creează o instanță a clasei.
Cu alte cuvinte, `__init__` este responsabilă pentru inițializarea atributelor obiectului cu valorile specificate atunci când obiectul este creat.

Pe scurt:

1. **Constructor:** `__init__` servește ca un constructor pentru obiectele clasei. Atunci când se creează o instanță a clasei, această metodă este apelată automat.

2. **Parametri:** `self` este un parametru special care reprezintă instanța obiectului care va fi creat. Alți parametri ai metodei sunt folosiți pentru a furniza informații inițiale pentru obiect.

3. **Inițializare a atributelor:** În cadrul metodei `__init__`, puteți inițializa atributele obiectului cu valorile corespunzătoare. Atributele sunt variabilele asociate cu obiectul.

Exemplul dat în introducerea la clasele Python arată cum `__init__` este folosit. Iată o parte a codului relevant:

```python
class Masina:
    # ...

    # Metoda constructor (inițializare)
    def __init__(self, marca, model, an_fabricatie):
        self.marca = marca
        self.model = model
        self.an_fabricatie = an_fabricatie
```

În acest exemplu, atunci când creați o instanță a clasei `Masina` prin `masina_mea = Masina("Toyota", "Corolla", 2020)`, metoda `__init__` este apelată automat, iar atributele `marca`, `model` și `an_fabricatie` ale obiectului `masina_mea` sunt inițializate cu valorile specificate.

Pe scurt, `__init__` este esențial în programarea orientată pe obiect pentru a asigura inițializarea corectă a obiectelor create dintr-o clasă.

## self

`self` este un cuvânt-cheie special în Python și este folosit pentru a face referire la instanța obiectului în cadrul metodelor unei clase. Acesta nu este un cuvânt rezervat strict, dar este o convenție în Python să folosiți `self` ca primul parametru al metodelor de clasă.

Pe scurt:

1. **Referire la Instanță:** Atunci când definiți metode într-o clasă, primul parametru ar trebui să fie `self`. Această convenție face ca metoda să poată accesa și modifica atributele clasei și să interacționeze cu instanța obiectului.

2. **Numire Convențională:** Deși puteți folosi orice nume în loc de `self` pentru primul parametru al unei metode de clasă, este o practică comună și o convenție să utilizați `self`. Acest lucru face codul mai ușor de înțeles și de citit pentru alți programatori.

3. **Legătură cu Instanța:** Când apelați o metodă a unei instanțe a clasei, Python se ocupă automat de transmiterea referinței la instanța (adică `self`). De exemplu, în apelul `masina_mea.afiseaza_informatii()`, Python în spatele scenei transmite `masina_mea` ca valoare pentru `self`.

Iată un exemplu pentru a ilustra utilizarea `self` în metoda `__init__` a unei clase:

```python
class Masina:
    def __init__(self, marca, model, an_fabricatie):
        # Utilizarea lui self pentru a face referire la instanța obiectului
        self.marca = marca
        self.model = model
        self.an_fabricatie = an_fabricatie

    def afiseaza_informatii(self):
        # Utilizarea lui self pentru a accesa atributele instanței
        print(f"Mașina {self.marca} {self.model}, fabricată în {self.an_fabricatie}")
```

În acest exemplu, `self` este folosit pentru a face referire la instanța curentă a clasei (`Masina`). Când apelați metoda `afiseaza_informatii()`, `self` se referă la instanța respectivă a clasei, permitându-vă să accesați și să utilizați atributele acelei instanțe.

## __str__

Metoda `__str__` este o altă metodă specială în Python, iar scopul său este să furnizeze o reprezentare ușor de citit a unui obiect sub formă de șir de caractere. Atunci când folosiți funcția `str()` sau funcția `print()` pentru a afișa un obiect, Python va încerca să apeleze automat metoda `__str__` a obiectului respectiv pentru a obține o reprezentare text.

Iată un exemplu simplu pentru a ilustra utilizarea metodei `__str__`:

```python
class Masina:
    def __init__(self, marca, model, an_fabricatie):
        self.marca = marca
        self.model = model
        self.an_fabricatie = an_fabricatie

    def __str__(self):
        # Returnează o reprezentare sub formă de șir de caractere a obiectului
        return f"Mașina {self.marca} {self.model}, fabricată în {self.an_fabricatie}"

# Crearea unei instanțe a clasei
masina_mea = Masina("Toyota", "Corolla", 2020)

# Utilizarea metodei __str__ prin intermediul funcției print
print(masina_mea)
```

În acest exemplu, metoda `__str__` este definită în cadrul clasei `Masina`. Când se utilizează funcția `print(masina_mea)`, Python va apela automat `__str__` pentru a obține o reprezentare sub formă de șir de caractere a obiectului `masina_mea`. Acest lucru oferă o modalitate convenabilă de a controla modul în care obiectele sunt reprezentate textual.

Folosirea metodei `__str__` este utilă în special atunci când doriți să oferiți o reprezentare ușor de înțeles a obiectelor pentru a facilita depanarea și înțelegerea codului.

## Exerciții

1. **Creați o clasă pentru un Telefon:**
   - Definiți o clasă `Telefon` cu următoarele atribute: `marca`, `model` și `pret`. Utilizați metoda `__init__` pentru a inițializa aceste atribute. Adăugați, de asemenea, o metodă `__str__` pentru a afișa informațiile despre telefon sub formă de șir de caractere.

2. **Gestiunea Studenților:**
   - Creați o clasă `Student` cu atributele `nume`, `varsta` și `note` (o listă de note). Utilizați metoda `__init__` pentru a inițializa aceste atribute. Adăugați, de asemenea, o metodă `__str__` care să afișeze informațiile despre student sub formă de șir de caractere.

```python
# Exemplu de utilizare
student1 = Student("Alice", 20, [8, 9, 7])
print(student1)
```
