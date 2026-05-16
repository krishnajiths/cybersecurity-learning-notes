## Cryptography

- **Symmetric encryption:** uses a single key for both encryption and decryption. It's fast and efficient, but you need a secure way to share that key. We used the Caesar cipher to see how this works.
- **Asymmetric encryption:** uses two linked keys: a public key that anyone can use and a private key that only one person keeps. This solves the key distribution problem and powers the initial handshake for HTTPS connections.
 *(Asymmetric key solves key distribution problem)*
 
  - Asymmetric encryption sets up a shared key at the start.
  - Symmetric encryption handles the actual data because it's faster.
  
 # Encryption
- **AES:** The Advanced Encryption Standard (AES) is a symmetric-key block cipher algorithm used globally to secure electronic data by transforming plaintext into unreadable ciphertext.

- **Block v. Stream encryption:** Block encryption handles data in chunks (blocks) like a factory assembly line, while stream encryption handles a continuous flow of bits like a flowing river of data.
