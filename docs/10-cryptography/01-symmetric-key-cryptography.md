---
nav_order: 1
title: Criptare cu cheie simetrica
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

# Criptare cu cheie simetrica

Criptarea este procesul de transformare a datelor într-o formă ilegibilă sau neinteligibilă pentru a proteja informațiile în timpul transmiterii sau stocării acestora. Scopul principal al criptării este să se asigure că doar persoanele autorizate, care dețin cheia de decriptare corespunzătoare, pot accesa și înțelege informațiile.

Există două tipuri principale de criptare:

1. **Criptare cu cheie simetrică:**
   - Utilizează aceeași cheie pentru atât criptare, cât și decriptare.
   - Este eficientă și rapidă, dar implică provocări legate de securitatea distribuirii cheii între părți.
   - Însă este dificilă împărțirea și menținerea secretă a cheii între interlocultori aflați la distanțe mari sau care comunică prin internet (un mediu nesigur). 
   - Exemplu: Criptarea AES (Advanced Encryption Standard).

2. **Criptare cu cheie asimetrică:**
   - Folosește o pereche de chei: una publică și una privată.
   - Cheia publică este folosită pentru criptare, iar cheia privată este utilizată pentru decriptare.
   - Este mai sigură din perspectiva distribuirii cheilor, dar poate fi mai lentă decât criptarea simetrică.
   - Exemple: RSA, ECC (Elliptic Curve Cryptography).

Pașii principali ai criptării sunt:

1. **Selectarea algoritmului și a cheilor:** Se alege algoritmul corespunzător de criptare și se generează cheile necesare (cheie simetrică sau pereche de chei publice și private).

2. **Criptarea datelor:** Datele sunt transformate într-o formă ilegibilă (criptată) folosind cheia aleasă și algoritmul de criptare.

3. **Transmiterea sau stocarea datelor criptate:** Datele criptate sunt trimise sau stocate într-un mod sigur, astfel încât doar destinatarul autorizat să aibă acces la cheia de decriptare.

4. **Decriptarea datelor:** Destinatarul autorizat primește datele criptate și le decriptează folosind cheia corespunzătoare, transformându-le înapoi în forma lor originală.

Criptarea este folosită în domenii precum securitatea informațiilor, protejarea datelor personale, securitatea comunicațiilor online, autentificare și în multe alte contexte în care protejarea informațiilor sensibile este crucială.

## One-time-pad (OTP)

One-time pad este o tehnică de criptare foarte sigură și este una dintre cele mai securizate modalități de a cripta datele. Ideea din spatele one-time pad constă în utilizarea unei chei secrete care este de lungime egală sau mai mare decât mesajul pe care îl criptezi. Această cheie este utilizată doar o singură dată și trebuie să fie generată complet aleatoriu.

În limbajul Python, putem implementa one-time pad astfel:

1. **Generarea unei chei aleatoare:**
   Pentru a genera o cheie aleatoare, putem folosi modulul `secrets` pentru a asigura generarea unei secvențe criptografic sigure de numere aleatoare.

2. **Criptarea și decriptarea:**
   - Mesajul original și cheia generată trebuie să aibă aceeași lungime.
   - Criptarea se realizează prin aplicarea operației XOR (sau "sau exclusiv") între mesajul original și cheia generată.
   - Decriptarea se face aplicând din nou operația XOR între textul criptat și cheia.

Iată un exemplu simplu în Python:

```python
import secrets

def generate_key(message_length):
    # Generare cheie aleatoare de lungimea specificată pentru mesaj
    return bytes([secrets.randbelow(256) for _ in range(message_length)])

def encrypt(message, key):
    # Criptare folosind operația XOR
    encrypted = bytes([message[i] ^ key[i] for i in range(len(message))])
    return encrypted

def decrypt(encrypted, key):
    # Decriptare folosind operația XOR
    decrypted = bytes([encrypted[i] ^ key[i] for i in range(len(encrypted))])
    return decrypted

# Mesajul pe care vrem să-l criptăm
message = b"Aceasta este o metoda de criptare one-time pad"

# Generăm o cheie aleatoare de aceeași lungime cu mesajul
key = generate_key(len(message))

# Criptăm mesajul
encrypted_message = encrypt(message, key)
print("Mesaj criptat:", encrypted_message)

# Decriptăm mesajul
decrypted_message = decrypt(encrypted_message, key)
print("Mesaj decriptat:", decrypted_message)
```

Trebuie să reținem că one-time pad are câteva cerințe esențiale pentru securitatea sa:
- Cheia trebuie să fie generată complet aleatoriu și să fie la fel de lungă sau mai lungă decât mesajul.
- Cheia trebuie păstrată în siguranță și transmisă în mod securizat destinatarului.
- Cheia trebuie folosită o singură dată și apoi distrusă. Dacă cheia este reutilizată, securitatea one-time pad este compromisă.

Această metodă este considerată imbatabilă atunci când este folosită corect, dar necesită o gestionare foarte atentă a cheilor și a procesului de generare a acestora.

## AES

AES (Advanced Encryption Standard) este un algoritm de criptare simetrică folosit pe scară largă pentru securizarea datelor. Este considerat un standard de facto și este utilizat în multe aplicații și sisteme de securitate.

În Python, pentru a utiliza AES pentru criptare și decriptare, putem folosi biblioteca `Crypto` (din pachetul `pycryptodome`). Iată un exemplu simplu de criptare și decriptare folosind AES în Python:

```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes
from Crypto.Util.Padding import pad, unpad
import base64

def generate_key():
    # Generare cheie AES de 256 de biți (32 de caractere)
    return get_random_bytes(32)

def encrypt(message, key):
    # Inițializare obiect AES cu modul de operare și cheie
    cipher = AES.new(key, AES.MODE_CBC)

    # Adăugare padding la mesaj pentru a fi multiplu de 16 bytes (lungimea blocului pentru AES)
    padded_message = pad(message.encode(), AES.block_size)

    # Criptare mesaj
    ciphertext = cipher.encrypt(padded_message)

    # Returnare mesaj criptat și IV (Vector de Inițializare)
    return ciphertext, base64.b64encode(cipher.iv)

def decrypt(encrypted_message, key, iv):
    # Inițializare obiect AES cu modul de operare, cheie și IV
    cipher = AES.new(key, AES.MODE_CBC, base64.b64decode(iv))

    # Decriptare mesaj
    decrypted_message = cipher.decrypt(encrypted_message)

    # Eliminare padding pentru a obține mesajul original
    original_message = unpad(decrypted_message, AES.block_size)

    # Returnare mesaj decriptat sub formă de string
    return original_message.decode()

# Mesajul pe care vrem să-l criptăm
message = "Acesta este un mesaj secret!"

# Generăm o cheie pentru criptare AES
key = generate_key()

# Criptăm mesajul
encrypted_message, iv = encrypt(message, key)
print("Mesaj criptat:", encrypted_message)
print("IV:", iv)

# Decriptăm mesajul
decrypted_message = decrypt(encrypted_message, key, iv)
print("Mesaj decriptat:", decrypted_message)
```

**Atenție!** Este nevoie să instalați pachetul `pycryptodome` folosind `pip install pycryptodome`.

În acest cod, se definesc două funcții principale: `encrypt` și `decrypt`. Funcția `encrypt` primește un mesaj și o cheie, creează un obiect AES, criptează mesajul folosind cheia și un IV (Vector de Inițializare), și returnează mesajul criptat și IV-ul. Funcția `decrypt` primește mesajul criptat, cheia și IV-ul și decriptează mesajul înapoi la forma sa originală.

Este important să menționăm că cheia trebuie păstrată în siguranță, deoarece accesul la cheie permite decriptarea datelor criptate. De asemenea, IV-ul trebuie transmis împreună cu mesajul criptat pentru a permite decriptarea corectă a datelor.

## Exerciții

1. Creați o funcție în Python care primește un mesaj de la utilizator și îl criptează folosind atât prin one-time pad cât și prin AES. Generați o cheie aleatoare și folosiți-o pentru criptare și decriptare.

1. Creați un program care primește două fișiere de intrare: un fișier text pentru criptat și un fișier cu cheia secretă (de lungime egală sau mai mare decât mesajul). Implementați funcții pentru criptarea și decriptarea conținutului fișierului text folosind one-time pad și cheia secretă.

1. Creați un sistem de chat simplu în Python care permite utilizatorilor să afișeze mesaje criptate folosind one-time pad. La fiecare nou mesaj se va genera o cheie aleatoare nouă care se va afișa împreună cu mesajul criptat.
Puteți citi date de la tastatură folosind funcția [`input()`](https://docs.python.org/3/library/functions.html#input).

1. Construiți un sistem de criptare a fișierelor folosind AES. Implementați un program care permite utilizatorului să trimită un nume de fișier necriptat de input și numele fișierului criptat așteptat.
Programul va cripta fișierul de input și va stoca datele criptate în cel de output.
