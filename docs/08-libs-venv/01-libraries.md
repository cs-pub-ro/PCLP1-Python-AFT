---
nav_order: 1
title: Biblioteci in Python
parent: Instalarea bibliotecilor și utilizarea mediilor virtuale
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Bibliotecile în Python sunt colecții de cod predefinite sau create de alți dezvoltatori, care extind funcționalitățile limbajului de bază. Ele sunt esențiale pentru a rezolva o varietate de probleme și pentru a construi aplicații mai complexe. Bibliotecile sunt utile pentru că oferă funcții, clase și instrumente specializate care permit dezvoltatorilor să evite rescrierea codului și să accelereze procesul de dezvoltare.

Iată de ce sunt bibliotecile atât de importante și de ce uneori ai nevoie de mai mult decât ce oferă biblioteca standard:

1. **Extindere funcțională:** Bibliotecile adaugă funcționalități noi și avansate în Python. De exemplu, biblioteca `numpy` oferă un set extins de funcții pentru lucrul cu matrici și vectori în comparație cu funcționalitățile matematice de bază.

2. **Eficiență în dezvoltare:** Utilizând bibliotecile, poți accesa funcționalități complexe cu un efort redus. De exemplu, `pandas` oferă instrumente puternice pentru lucrul cu seturi de date tabulare, facilitând operațiuni precum filtrarea, gruparea și analiza datelor.

3. **Specializare:** Bibliotecile sunt create pentru a rezolva probleme specifice. De exemplu, `tensorflow` și `pytorch` sunt biblioteci puternice pentru dezvoltarea și implementarea modelelor de învățare automată și de învățare profundă.

4. **Comunitatea și colaborarea:** Dezvoltatorii contribuie la diverse biblioteci, adăugând noi funcționalități, îmbunătățind performanța și rezolvând problemele. Aceasta înseamnă că poți beneficia de experiența și contribuția altora pentru a rezolva sarcinile tale.

5. **Soluții rapide și robuste:** Bibliotecile bine dezvoltate au fost testate și optimizate, oferind soluții robuste și eficiente pentru probleme specifice.

Chiar și cu o bibliotecă standard bogată în Python, există necesitatea de a folosi alte biblioteci specializate pentru a face față unor sarcini mai complexe sau pentru a obține performanțe mai bune. De exemplu, pentru manipularea datelor, poți folosi `pandas`, iar pentru procesarea imaginilor, `opencv` poate fi o alegere excelentă.

Exemplu de cod:

```python
# Exemplu cu pandas pentru a încărca și afișa date
import pandas as pd

# Încărcare date dintr-un fișier CSV
data = pd.read_csv('date.csv')

# Afișare primele câteva rânduri din setul de date
print(data.head())
```

## Instalarea Bibliotecilor

În afara bibliotecii standard Python, există o bogată varietate de alte biblioteci disponibile, iar acestea sunt adesea găzduite în diferite locuri online, ceea ce vă permite să le accesați și să le instalați pentru a extinde funcționalitatea limbajului.

Iată câteva locuri comune unde puteți găsi și accesa biblioteci Python suplimentare:

1. **Python Package Index (PyPI):** PyPI este cea mai populară resursă pentru bibliotecile Python. Aici găsiți mii de pachete disponibile pentru instalare folosind `pip`. Accesați PyPI la adresa https://pypi.org/.

2. **GitHub:** Mulți dezvoltatori și echipe își găzduiesc bibliotecile Python pe platforma GitHub. Puteți căuta și accesa aceste biblioteci folosind căutarea GitHub la adresa https://github.com/.

3. **Conda și Anaconda:** Conda este un sistem de gestionare a pachetelor care vine împreună cu distribuția Anaconda. Anaconda oferă o colecție largă de pachete Python, în special pentru domeniile științifice și de analiză a datelor. Puteți accesa Anaconda la adresa https://www.anaconda.com/.

4. **Site-uri specializate:** Există site-uri și platforme specializate care găzduiesc biblioteci pentru domenii specifice, cum ar fi machine learning, web development sau data science. De exemplu, pentru machine learning, puteți accesa TensorFlow (https://www.tensorflow.org/) sau PyTorch (https://pytorch.org/).

Exemplu de instalare a unei biblioteci de pe PyPI folosind `pip`:

```bash
pip install nume_bibliotecă
```

Exemplu de căutare a unei biblioteci pe GitHub și instalare folosind `pip`:

1. Găsiți biblioteca pe GitHub.
2. Accesați secțiunea `Clone or download` și copiați URL-ul.
3. Instalați biblioteca folosind `pip` și URL-ul:
   
   ```bash
   pip install git+URL-ul_bibliotecii.git
   ```

De asemenea, este important să fiți atenți la documentația și recomandările de instalare pentru fiecare bibliotecă specifică. Aceste resurse online sunt excelente pentru a găsi și a accesa biblioteci Python care vă pot ajuta în proiectele voastre.

## Package Managerul `pip`

Un package manager este o unealtă software care facilitează descărcarea, instalarea, actualizarea și gestionarea pachetelor de software sau a bibliotecilor necesare pentru un proiect sau un sistem de calcul. În esență, ajută la gestionarea dependențelor și a versiunilor diferitelor pachete sau biblioteci software.

Python folosește `pip` ca principalul său package manager. `pip` este un instrument de linie de comandă care vine împreună cu instalarea Python și este utilizat pentru a instala și gestiona pachetele Python. Acesta interacționează cu Python Package Index (PyPI), o colecție vastă de pachete Python care sunt disponibile pentru instalare.

Iată câteva comenzi de bază `pip`:

1. **Instalarea unei biblioteci:**
   
   Pentru a instala o bibliotecă, utilizați comanda `pip install nume_bibliotecă`. De exemplu, pentru a instala biblioteca `requests`:

   ```bash
   pip install requests
   ```

2. **Listarea pachetelor instalate:**
   
   Pentru a vedea lista pachetelor Python instalate, utilizați comanda `pip list`:

   ```bash
   pip list
   ```

3. **Actualizarea unei biblioteci:**
   
   Pentru a actualiza o bibliotecă la cea mai recentă versiune, utilizați comanda `pip install --upgrade nume_bibliotecă`. De exemplu, pentru a actualiza `requests`:

   ```bash
   pip install --upgrade requests
   ```

4. **Ștergerea unei biblioteci:**
   
   Pentru a dezinstala o bibliotecă, utilizați comanda `pip uninstall nume_bibliotecă`. De exemplu, pentru a dezinstala `requests`:

   ```bash
   pip uninstall requests
   ```

5. **Instalarea pachetelor dintr-un fișier `requirements.txt`:**
   
   Puteți instala mai multe pachete simultan dintr-un fișier `requirements.txt` folosind comanda `pip install -r requirements.txt`. Acest fișier conține lista pachetelor și versiunile pe care doriți să le instalați.

   Exemplu de conținut pentru `requirements.txt`:

   ```
   requests==2.26.0
   numpy==1.21.2
   pandas==1.3.3
   ```

   Pentru a instala pachetele enumerate în `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

`pip` este un instrument esențial în ecosistemul Python, care vă permite să gestionați ușor pachetele și dependențele proiectelor dumneavoastră. Utilizând `pip`, puteți accesa, instala și gestiona o varietate largă de pachete Python pentru a vă îndeplini necesitățile de dezvoltare a software-ului.

## Exerciții

Instalați biblioteca `matplotlib`, folosită pentru desenarea de grafice.
Pentru următoarele exerciții veți avea nevoie să consultați [documentația bibliotecii](https://matplotlib.org/stable/api/index.html), pentru a găsi funcțiile de care aveți nevoie,

1. Creați două liste de valori x și y și trasați un grafic al valorilor `y` în funcție de `x` folosind `matplotlib`.
Folosiți funcțiile `matplotlib.pyplot.plot()` și `matplotlib.pyplot.show()`.
Adăugați o a 3-a listă `z` și afișați-i graficul in aceeași imagine.

1. Adăugați denumiri pentru cele două axe astfel încât datele să aibă sens.
Folosiți orice denumiri și unități de măsură vreți.

1. Acum folosiți `subplot()` pentru a afișa graficul listei `z` într-o figură alăturată de cea în care este afișat `x`.

1. Generați date pentru a reprezenta vânzările zilnice ale unui magazin într-o săptămână și trasați un grafic de bare pentru aceste date.
Pentru a nu încărca prea mult figura, folosiți 5 tipuri de produse.

1. Generați o listă de 100 de numere aleatoare (importand modulul `random`) și trasați un histogramă pentru a vizualiza distribuția lor.
