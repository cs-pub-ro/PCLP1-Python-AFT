---
nav_order: 1
title: Introducere în limbajul Python
has_children: true
---
# Introducere în limbajul Python

Python este un limbaj de programare foarte popular ([statistici github](https://octoverse.github.com/), [utilizare](https://realpython.com/blog/python/world-class-companies-using-python/)), oferind posibilitatea programării structurate dar și orientate pe obiect și incluzând și elemente din paradigma funcțională.
Este un limbaj de scripting, ceea ce înseamnă că este interpretat și nu compilat, economisind mult timp în procesul de dezvoltare și debugging.

Limbajul oferă o multitudine de funcționalități într-o sintaxă ușor de învățat.
Are module, clase, excepții, tipuri dinamice și garbage collection.
[Biblioteca standard](http://docs.python.org/3/library/) Python oferă module pentru o gamă foarte [mare](http://xkcd.com/353/) de funcționalități, de la cele de bază pentru lucrul cu șiruri și fișiere, până la cele pentru lucrul cu procese, threaduri, sockets, serializare etc.
Multe dintre aceste module oferă o interfață foarte similară programării la nivel de sistem din C (ceea ce se studiază la Sisteme de Operare), astfel încât funcțiile Python au același nume si aproximativ aceiași parametrii ca cei pentru funcțiile din C pentru apeluri de sistem.
Există o varietate de biblioteci, cele mai populare la momentul actual fiind cele pentru aplicatii web, AI bots, data science si grafice, de exemplu:
[wit.ai](https://github.com/wit-ai/pywit), [flask](http://flask.pocoo.org/), [NumPy](http://www.numpy.org/), [SciPy](http://www.scipy.org/), [pandas](https://pandas.pydata.org/), [plotly](https://plot.ly/d3-js-for-python-and-pandas-charts/), [Matplotlib](http://matplotlib.org/), [Python & RaspberryPi](https://www.raspberrypi.org/documentation/usage/python/).

Implementarea principală a Python, [CPython](http://en.wikipedia.org/wiki/CPython) (în C) a fost concepută pentru a fi portabilă: funcționează pe Linux, Unix, Windows, Mac OS X.

## Python este un limbaj interpretat. Ce înseamnă asta?

Fiind un limbaj interpretat înseamnă că codul Python este executat linie cu linie în timpul rulării de către interpretorul Python, în loc să fie compilat în cod mașină înainte de execuție. Iată o desfășurare a ceea ce înseamnă acest lucru:

1. **Fără Etapă de Compilare:** Spre deosebire de limbaje precum C sau C++, unde trebuie să compilați codul sursă în cod mașină înainte de a rula programul, Python nu necesită o etapă separată de compilare. Puteți rula codul Python direct fără a avea nevoie de un proces de compilare explicit.

2. **Execuția Codului Sursă:** În Python, codul sursă este citit de interpretor, iar instrucțiunile sunt executate una câte una. Interpretorul traduce codul de nivel înalt în cod intermediar (bytecode) sau cod mașină specific platformei în timpul rulării.

3. **Portabilitate:** Deoarece codul Python nu este compilat în instrucțiuni specifice platformei în prealabil, programele Python sunt în general mai portabile. Puteți scrie un script Python pe un sistem de operare (de exemplu, Windows) și să-l rulați pe altul (de exemplu, Linux) fără modificări, atâta timp cât sistemul țintă are un interpretor Python compatibil.

4. **Ușurința la Debugging:** Limbajele interpretate oferă adesea un suport mai bun pentru debugging, deoarece erorile sunt raportate la locul din cod unde apar. Dezvoltatorii pot testa și modifica interactiv codul în timpul dezvoltării, facilitând procesul de debugging.

5. **Execuție Mai Lentă:** Limbajele interpretate, în general, pot avea un cost suplimentar de performanță în comparație cu limbajele compilate în cod mașină. Cu toate acestea, avansurile precum compilarea la cerere (JIT) și optimizările în interpretorul Python au îmbunătățit semnificativ performanța acestuia.

6. **Flexibilitate și Tipare Dinamică:** Interpretarea permite o mai mare flexibilitate și caracteristici dinamice în limbaj. De exemplu, Python este un limbaj cu tipare dinamic, ceea ce înseamnă că tipurile de variabile sunt determinate în timpul rulării. Această flexibilitate vine însă cu costul potențialelor erori în timpul rulării dacă problemele legate de tipuri nu sunt gestionate cu atenție.

Sumarizând, faptul că Python este un limbaj interpretat înseamnă că codul său sursă este executat direct de către interpretorul Python în timpul rulării, oferind avantaje în ceea ce privește portabilitatea, ușurința la debugging și flexibilitatea, cu eventuale compromisuri în ceea ce privește viteza de execuție.
