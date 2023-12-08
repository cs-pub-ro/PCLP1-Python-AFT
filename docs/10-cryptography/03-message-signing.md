---
nav_order: 3
title: Semnarea mesajelor
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

Semnarea mesajelor este un proces prin care se asigură integritatea, autenticitatea și ne-repudierea mesajului. În esență, semnarea unui mesaj implică aplicarea unei semnături digitale unice și criptografice asupra mesajului, folosind o cheie privată.

În Python, putem utiliza biblioteca `Crypto` (din pachetul `pycryptodome`) pentru a implementa semnarea mesajelor folosind algoritmul de semnătură digitală RSA. Iată un exemplu simplu:

```python
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generare de pereche de chei RSA (4096 biți)
key = RSA.generate(4096)

# Obținerea cheii publice și a celei private
public_key = key.publickey()
private_key = key

# Mesajul pe care vrem să-l semnăm
message = b"Acesta este un mesaj pe care vrem să-l semnăm."

# Calcularea hash-ului mesajului
hash_message = SHA256.new(message)

# Semnarea hash-ului mesajului cu cheia privată
signature = pkcs1_15.new(private_key).sign(hash_message)
print("Semnătura digitală:", signature)

# Verificarea semnăturii folosind cheia publică
try:
    pkcs1_15.new(public_key).verify(hash_message, signature)
    print("Semnătura este autentică.")
except (ValueError, TypeError):
    print("Semnătura NU este autentică.")
```

În acest exemplu:

1. Se generează o pereche de chei RSA de 4096 de biți.
2. Se obțin cheia publică și cea privată din perechea generată.
3. Se creează un mesaj pe care dorim să-l semnăm și se calculează hash-ul acestuia (în exemplul dat, se folosește algoritmul SHA256 pentru a genera hash-ul mesajului).
4. Se semnează hash-ul mesajului folosind cheia privată pentru a obține semnătura digitală.
5. Se verifică semnătura digitală folosind cheia publică.

În procesul de semnare și verificare, cheia privată este folosită pentru a crea semnătura, iar cheia publică este folosită pentru a verifica dacă semnătura corespunde mesajului și a garanta astfel autenticitatea și integritatea acestuia.

Semnăturile digitale sunt utilizate pentru a verifica sursa și autenticitatea datelor într-o comunicare și sunt un instrument esențial în securitatea informatică, în special în autentificarea și protejarea integrității datelor în medii digitale.

## Exerciții

1. Creați o clasă `MessageSigner` care să permită unui utilizator să introducă un mesaj, să îl semneze folosind cheia privată și să verifice semnătura folosind cheia publică asociată.

1. Implementați o clasă `DocumentManager` care să primească un document text, să îl semneze folosind o cheie privată și să stocheze documentul semnat împreună cu semnătura într-o structură de date adecvată.
Folosiți o structură de date precum un dicționar pentru a stoca documentul și semnătura asociată.

1. Creați o aplicație Python care să simuleze un sistem de semnare și verificare a mesajelor între diferite entități. Implementați această funcționalitate folosind chei publice și private pentru semnarea și verificarea mesajelor.

- **Clase:**
  - Definiți o clasă `Entity` care să reprezinte o entitate care poate semna și verifica mesaje.
  - În cadrul clasei `Entity`, implementați metode pentru generarea perechii de chei publice și private, semnarea mesajelor și verificarea semnăturilor.

- **Semnare și verificare:**
  - O entitate (o instanță a clasei `Entity`) trebuie să poată semna un mesaj (string) folosind cheia sa privată și să genereze o semnătură.
  - Alte entități pot verifica semnătura unui mesaj folosind cheia publică corespunzătoare entității care a semnat mesajul.

- **Structuri de date:**
  - Folosiți un dicționar pentru a stoca entitățile și cheile lor publice și private.

- **Interacțiunea:**
  - Implementați un sistem simplu de consolă pentru a permite utilizatorului să creeze, să semneze și să verifice mesaje între diferite entități.

Acestea sunt pașii de bază pentru exercițiul propus. Puteți extinde acest exercițiu adăugând funcționalități suplimentare, cum ar fi gestionarea unui număr mai mare de entități, stocarea cheilor în fișiere etc.

Un exemplu simplu de structură ar putea arăta în felul următor:

```python
# Exemplu de utilizare:
entity_A = Entity("Entity A")
entity_B = Entity("Entity B")

entity_A.generate_keys()
entity_B.generate_keys()

entities = {
    "Entity A": entity_A,
    "Entity B": entity_B,
}

# Semnare mesaj de către Entity A
message_to_sign = "Mesaj semnat de către Entity A"
signature = entities["Entity A"].sign_message(message_to_sign)

# Verificare semnătură de către Entity B folosind cheia publică a Entity A
verified = entities["Entity B"].verify_signature(message_to_sign, signature, entities["Entity A"].public_key)
print(f"Semnătura este autentică: {verified}")
```
