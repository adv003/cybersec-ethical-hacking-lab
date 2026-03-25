# Cryptography Basics

## Symmetric vs Asymmetric Encryption
| Type | Key | Speed | Use case | Example |
|------|-----|-------|----------|---------|
| Symmetric | Same key to encrypt/decrypt | Fast | Bulk data encryption | AES-256 |
| Asymmetric | Public key encrypts, private key decrypts | Slow | Key exchange, signatures | RSA-2048 |

## Hashing
- One-way function — cannot be reversed
- Same input always produces same output
- Any change in input produces completely different hash

| Algorithm | Output size | Status |
|-----------|-------------|--------|
| MD5 | 128-bit | Broken — collision attacks exist |
| SHA-1 | 160-bit | Deprecated |
| SHA-256 | 256-bit | Secure — widely used |

## Digital Certificates & SSL/TLS
- Certificate Authority (CA) signs a server's public key
- Browser trusts the CA → trusts the certificate → establishes encrypted session
- TLS 1.3 is current standard — TLS 1.0/1.1 deprecated

## OpenSSL Hands-on
```bash
# Generate a private key
openssl genrsa -out private.key 2048

# Encrypt a message (symmetric AES-256)
openssl enc -aes-256-cbc -salt -in plaintext.txt -out encrypted.enc

# Decrypt it
openssl enc -aes-256-cbc -d -in encrypted.enc -out decrypted.txt

# Hash a file
openssl dgst -sha256 plaintext.txt

# Generate a self-signed certificate
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout selfsigned.key -out selfsigned.crt
```
## OpenSSL Note
The -pbkdf2 flag uses Password-Based Key Derivation Function 2 to 
derive the encryption key from the password. Without it, OpenSSL 
uses a weaker legacy method and throws a deprecation warning.
Always use -pbkdf2 with modern OpenSSL versions.

`rsautl` was deprecated in OpenSSL 3.0. Use `pkeyutl` instead 
for RSA encryption/decryption operations. The flags remain 
the same — only the command name changes.
