# Cryptography

<p align="center">
<img width="70%" src="https://cdn.ttgtmedia.com/rms/onlineImages/security_cissp_cryptography_mobile.jpg" />
</p>

## Symmetric cryptography
  - Use the same key for the encryption and the decryption
  - The encryption process is very fast.
  - Popular algorithms: AES, DES

## Asymmetric / Public Key cryptography
  - Two key used: public and private
  - Public key is publicly known to everyone, issued by Public Key Infrastructure (PKI) and use to encrypt the data
  - Private key is a secret for the public,only known by the owner and it is used to decrypt the data
  - Asymmetric cryptography delivers confidentiality, integrity, authenticity and non-repudiation
  - Popular algorithms : RSA, DSA and Diffie-Hellman, ECDHA

## Substitution Cipher
  - Every character is substituted with another one
  - More on [Wikipedia](https://en.wikipedia.org/wiki/Substitution_cipher)
  - Example cipher : [Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

Example:
```
Plaintext :  THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG
Ciphertext : QEB NRFZH YOLTK CLU GRJMP LSBO QEB IXWV ALD

Key : right shift of 3
```

## Transposition Cipher
  - The positions held by units of plaintext are shifted according to a regular system
  - Example cipher [Rail Fence cipher](https://en.wikipedia.org/wiki/Rail_fence)

Example:
```
Clear text: WE ARE DISCOVERED. FLEE AT ONCE

W . . . E . . . C . . . R . . . L . . . T . . . E           00..........00..........00
. E . R . D . S . O . E . E . F . E . A . O . C .           ...00....00....00....00...
. . A . . . I . . . V . . . D . . . E . . . N . .           ......00..........00......

Ciphertext: WECRLTEERDSOEEFEAOCAIVDEN
```
## Data Encryption Standard (DES)
  - Introduced in 1975
  - Standardized in 1977 by NIST
  - Problem with DES: short key length (56 bits) -> ASICS Chips
  - Now considered as insecure
  - Improved version: Triple DES (involves DES three times)
  - Problem with Triple DES: slow, compute heavy

# Encryption Types: Symmetric vs. Asymmetric

| Aspect                 | Symmetric Encryption     | Asymmetric Encryption   |
|------------------------|--------------------------|-------------------------|
| Key Types              | Single shared key       | Key pair (public, private) |
| Security               | Fast and efficient      | More secure but slower  |
| Key Distribution       | Requires secure sharing | Public keys can be shared |
| Encryption/Decryption  | Same key for both       | Different keys for encryption and decryption |
| Use Cases              | Bulk data encryption     | Secure key exchange, digital signatures |
| Examples               | AES, DES, 3DES           | RSA, ECC, ElGamal       |

## <u>Hashes</u>

- **One-way encryption**
- **Verify the Integrity of the message.**

Hash | Algo.
--|--
MD5 | 128 bit hash
SHA-1 | 160 bit hash
SHA256 | 256 bit hash

*Examples*:
```console
String: hello world!

MD5 Hash: FC3FF98E8C6A0D3087D515C0473F8677
SHA-1 Hash: 430CE34D020724ED75A196DFC2AD67C77772D169
SHA256 Hash: 7509E5BDA0C762D2BAC7F90D758B5B2263FA01CCBC542AB5E3DF163BE08E6CA9
```

> ⚠️ If you change a single character, the entire Hash value changes. **See the example below, changing the last character '!' to '.'**

* String: **hello world!**
	- ```MD5 Hash: FC3FF98E8C6A0D3087D515C0473F8677```
* String: **hello world.**
	- ```MD5 Hash: 3C4292AE95BE58E0C58E4E5511F09647```

## <u>Cryptography Attacks</u>

- **Timing Attack**
  - Based on examining exact execution times of the components in the cryptosystems

- **Birthday Attack / Collision Attack / Reverse Hash matching**
  - Find flaws in the one-to-one association of the hash function

- **Side-Channel Attack**
  - Monitors environmental factors such as power consumption, timing and delay

- **Chosen Plain-text attack** 
  - Attacker encrypts multiple plain-text copies in order to gain the key

**Tools**
  - Carnivore and Magic Lantern - used by law enforcement for cracking codes
  - L0phtcrack - used mainly against Windows SAM files
  - John the Ripper - UNIX/Linux tool for the same purpose
  - PGPcrack - designed to go after PGP-encrypted systems
  - CrypTool
  - Cryptobench
  - Jipher

## How to defeat attack:

- **Salt the passwords** - A nonce most commonly associated with password randomization, making the password hash unpredictable.
  -  *If the password database is breached, you can't correlate any passwords because even users with the same password have different hashes stored.*
