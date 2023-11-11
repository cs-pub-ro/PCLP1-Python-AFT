---
title: Instalarea Interpretorului Python 
parent: Introducere în limbajul Python
nav_order: 1
---

# Instalarea Interpretorului Python

Python se poate descărca de pe [site-ul oficial](http://www.python.org/), secțiunea [Download](http://www.python.org/download/).

Pe un sistem Linux, este foarte probabil să fie deja instalat. Verificați acest lucru dintr-o consolă:
```bash
$ python
Python 3.9.16 (default, Dec  7 2022, 10:16:11)
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

Dacă nu îl aveți instalat, pasul următor ar fi să-l căutați în repository-urile distribuției Linux cu care lucrați.
Exemplele următoare prezintă instalarea pe o distribuție bazată pe Debian și pe una bazată pe Red Hat.

```bash
$ sudo apt-get update
$ sudo apt-get install python3
```
```bash
$ sudo yum install python3
```

Pe un system Windows se poate descărca de [aici](https://www.python.org/downloads).
După instalare se poate adăuga calea către executabilul Python în variabila globală PATH, pentru a putea fi folosit din orice terminal.
Acest lucru se poate face mai ușor selectând opțiunea Add Python to PATH la începutul instalării.