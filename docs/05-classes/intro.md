---
nav_order: 1
title: Clase
has_children: true
---

# Clase

În Python, clasele sunt un mod de a organiza și a grupa date și funcționalități într-o unitate logică.
O clasă este un tip de șablon sau plan pentru crearea obiectelor.

## Cum se definește o clasă?

```python
class Masina:
    # Atributele clasei
    marca = ""
    model = ""
    an_fabricatie = 0

    # Metoda constructor (inițializare)
    def __init__(self, marca, model, an_fabricatie):
        self.marca = marca
        self.model = model
        self.an_fabricatie = an_fabricatie

    # Metodele clasei
    def afiseaza_informatii(self):
        print(f"Mașina {self.marca} {self.model}, fabricată în {self.an_fabricatie}")

# Crearea unei instanțe a clasei
masina_mea = Masina("Toyota", "Corolla", 2020)

# Apelarea unei metode a instanței
masina_mea.afiseaza_informatii()
```

## Atribute și Metode

- **Atributele** sunt variabilele asociate cu o clasă și reprezintă caracteristicile obiectelor create din acea clasă.
  
- **Metodele** sunt funcțiile definite într-o clasă și sunt folosite pentru a efectua acțiuni legate de obiectele respective.

## Constructorul

Metoda `__init__` este un constructor special care se apelează atunci când o instanță a clasei este creată. Este folosită pentru inițializarea atributelor obiectului.

## Instanțierea unei clase

Creăm o instanță a clasei prin apelarea clasei ca pe o funcție. În exemplul de mai sus, `masina_mea` este o instanță a clasei `Masina`.

## Accesarea Atributelor

Putem accesa atributele unei instanțe folosind notația cu punct (`.`). De exemplu, `masina_mea.marca` ne va da valoarea atributului "marca" al obiectului `masina_mea`.

## Mostenirea

Python suportă și conceptul de moștenire. O clasă poate moșteni atribute și metode de la o altă clasă, ceea ce promovează reutilizarea codului.

```python
class MasinaElectrica(Masina):
    autonomie_km = 0

    def __init__(self, marca, model, an_fabricatie, autonomie_km):
        super().__init__(marca, model, an_fabricatie)
        self.autonomie_km = autonomie_km

    def afiseaza_informatii_electrica(self):
        print(f"Mașina electrică {self.marca} {self.model}, fabricată în {self.an_fabricatie}, cu o autonomie de {self.autonomie_km} km")
```
