---
nav_order: 2
title: Criptare cu chei publice si private
parent: Criptare și semnarea datelor
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Criptare asimetrică (cu chei publice si private)

Criptarea folosind chei publice și private este un aspect fundamental al criptografiei asimetrice. În acest context, fiecare entitate implicată în comunicare are o pereche de chei: o cheie publică și una privată. Cheia publică poate fi distribuită liber, în timp ce cheia privată rămâne secretă.

În limbajul Python, putem folosi biblioteca `Crypto` (din pachetul `pycryptodome`) pentru a lucra cu criptografia asimetrică. Unul dintre algoritmii asimetrici populari este RSA, iar biblioteca Crypto oferă facilități pentru lucrul cu acest algoritm. Iată un exemplu simplu de criptare folosind chei publice și private în Python:

```python
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Generare de pereche de chei RSA (4096 biți)
key = RSA.generate(4096)

# Obținerea cheilor publică și privată
public_key = key.publickey()
private_key = key

# Mesajul pe care vrem să-l criptăm
message = b"Acesta este un mesaj secret!"

# Criptarea mesajului folosind cheia publică
cipher = PKCS1_OAEP.new(public_key)
encrypted_message = cipher.encrypt(message)
print("Mesaj criptat:", encrypted_message)

# Decriptarea mesajului folosind cheia privată
cipher = PKCS1_OAEP.new(private_key)
decrypted_message = cipher.decrypt(encrypted_message)
print("Mesaj decriptat:", decrypted_message)
```

În acest exemplu, se realizează următoarele acțiuni:

1. Se generează o pereche de chei RSA de 4096 de biți.
2. Se obține cheia publică și cea privată din perechea generată.
3. Mesajul este criptat folosind cheia publică și apoi decriptat folosind cheia privată.

În esență, cheia publică este utilizată pentru criptare și poate fi distribuită în mod liber, iar cheia privată este utilizată pentru decriptare și trebuie păstrată în siguranță. Procesul de criptare și decriptare se bazează pe algoritmul RSA, iar biblioteca Crypto facilitează aceste operații prin intermediul metodelor precum `encrypt` și `decrypt` din modulul `Crypto.Cipher.PKCS1_OAEP`.

Este important să menționăm că RSA este un algoritm intensiv din punct de vedere al resurselor și este folosit mai mult pentru criptarea cheilor simetrice sau a semnăturilor digitale în loc de criptarea directă a datelor. În practică, criptografia asimetrică este adesea utilizată în combinație cu criptografia simetrică pentru a asigura securitatea comunicării și a transferului de date.

De aceea, abordarea utilizată în practică este aceea de a utiliza criptarea asimetrică pentru a schimba o cheie care apoi va fi folosită pentru criptarea simetrica a viitoarelor mesaje.
Această metodă este avantajoasă deoarece criptarea simetrică este mai eficientă din punct de vedere computațional decât cea asimetrică.
Acest lucru se datoreaza și algoritmilor de criptare în sine, dar și faptului că procesoarele moderne implementează nativ și optimizat în hardware-ul lor algoritmi de criptare precum AES.

## Exerciții

1. Creați o clasă `CryptoSystem` care să gestioneze criptarea și decriptarea unui mesaj folosind chei publice și private. Implementați metode pentru generarea perechii de chei, criptarea mesajului și decriptarea acestuia.

1. Creați o clasă `DocumentEncryptor` care să primească o lista de nume de documente text necriptate și să le cripteze folosind criptarea asimetrică cu chei publice și private. 
Numele documentelor criptate trebuie să fie stocate într-o listă. Acestea vor fi formate adăugând șirul `.enc` la finalul numelor fișierelor necriptate.
De exemplu, fișierul criptat corespunzător lui `file1.txt` va fi `file1.txt.enc`.

1. Simulați un sistem de comunicare între două entități (clase) care pot trimite și primi mesaje criptate folosind chei publice și private. Implementați un schimb securizat de mesaje între aceste două entități, unde fiecare entitate folosește perechea sa de chei publice și private pentru criptare și decriptare.
