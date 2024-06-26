## What  is it? 

**Transport Layer Security (TLS)** - a client / server protocol used to communicate securely across a network by using cryptographic protocols. It prevents eavesdropping or message tampering. 

## How does it work? 

Majority of a TLS connection is related with a TLS handshake. After the TCP connection is established and before any data is sent, the TLS handshake is made. 

### What is a cipher suite? 

It is a string representation of all things that will be done during a handshake, I.e. **TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256** 
- TLS - protocol being used
- ECDHE - key exchange method (in this example elliptic curve Diffie-Hellman)
- RSA - authentication mechanism
- AES  - symmetric encryption algorithm 
- 128 - key size for cipher 
- GCM - mode of operation
- SHA256 - hash function that will be used if it's needed

### TLS 1.2 handshake

![[../images/TLS handshake diagram.png]]


1. Client Hello - It starts a TLS handshake and contains:
	- max supported TLS version 
	- list of Cipher Suites that client supports
	- client random, which is large prime number, that makes sure that some attacks are not going to work 
2. Server Hello - It says what will be used in further steps of TLS handshake, meaning
	- chosen TLS version
	- chosen cipher suite (if there is no matching Cipher Suite found, then it sends an error)
	- server random (similar to client random, it is a server's own large prime number) 
3. Certificate - It sends an SSL/TLS certificate, that authenticates the server. 
4. Server Key Exchange - This is an optional message, sends when additional data is required for key exchange method (I.e. Diffie-Hellman) 
5. Server Hello Done - a message that says that server sent everything, that is required for establishing TLS connection 
6. Client Key Exchange - It contains client's data for key exchange operation
7. Change cipher spec message - It says to the server that next message will be encrypted because they've got what they need to encrypt that message. 
8. Finish - This message is encrypted and allows each party to make sure that the handshake is completed successfully. 
9. Change cipher spec - A message sent by a server that also communicate that next message will be encrypted
10. Finish - encrypted message sent by a server to be verified by a client 



# Sources
- https://www.youtube.com/watch?v=0TLDTodL7Lc
- https://developer.mozilla.org/en-US/docs/Glossary/TLS
- https://en.wikipedia.org//wiki/Cipher_suite
