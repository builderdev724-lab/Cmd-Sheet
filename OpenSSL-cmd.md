# OpenSSL Command Cheat Sheet

> A complete guide to OpenSSL commands for certificates, encryption, hashing, and SSL/TLS.

---

# Table of Contents

1. Installation
2. Version Information
3. Random Data
4. Hashing
5. Base64
6. Private Keys
7. Public Keys
8. Certificate Signing Request (CSR)
9. Self-Signed Certificates
10. Certificate Inspection
11. Certificate Conversion
12. PKCS#12 (.p12/.pfx)
13. Encryption & Decryption
14. SSL/TLS Testing
15. Verify Certificates
16. Common Problems
17. Developer Workflow
18. Essential Commands
19. Best Practices

---

# 1. Installation

Ubuntu

```bash
sudo apt install openssl
```

Version

```bash
openssl version
```

Detailed Version

```bash
openssl version -a
```

---

# 2. Random Data

Generate Random Hex

```bash
openssl rand -hex 32
```

Generate Random Base64

```bash
openssl rand -base64 32
```

Generate API Secret

```bash
openssl rand -hex 64
```

---

# 3. Hashing

SHA256

```bash
openssl dgst -sha256 file.txt
```

SHA512

```bash
openssl dgst -sha512 file.txt
```

MD5

```bash
openssl dgst -md5 file.txt
```

---

# 4. Base64

Encode

```bash
openssl base64 -in input.txt -out output.txt
```

Decode

```bash
openssl base64 -d -in output.txt -out input.txt
```

---

# 5. Private Keys

Generate RSA Key

```bash
openssl genrsa -out private.key 2048
```

Generate 4096-bit RSA Key

```bash
openssl genrsa -out private.key 4096
```

Generate EC Key

```bash
openssl ecparam \
-name prime256v1 \
-genkey \
-noout \
-out ec-private.key
```

---

# 6. Public Keys

Extract Public Key

```bash
openssl rsa \
-in private.key \
-pubout \
-out public.key
```

View Public Key

```bash
openssl rsa \
-pubin \
-in public.key \
-text \
-noout
```

---

# 7. Certificate Signing Request (CSR)

Generate CSR

```bash
openssl req \
-new \
-key private.key \
-out request.csr
```

View CSR

```bash
openssl req \
-in request.csr \
-noout \
-text
```

---

# 8. Self-Signed Certificate

Generate Certificate

```bash
openssl req \
-x509 \
-newkey rsa:2048 \
-keyout private.key \
-out certificate.crt \
-days 365
```

Without Passphrase

```bash
openssl req \
-x509 \
-nodes \
-newkey rsa:2048 \
-keyout private.key \
-out certificate.crt
```

---

# 9. Certificate Inspection

View Certificate

```bash
openssl x509 \
-in certificate.crt \
-text \
-noout
```

Check Expiration

```bash
openssl x509 \
-enddate \
-noout \
-in certificate.crt
```

Issuer

```bash
openssl x509 \
-noout \
-issuer \
-in certificate.crt
```

Subject

```bash
openssl x509 \
-noout \
-subject \
-in certificate.crt
```

---

# 10. Certificate Conversion

PEM → DER

```bash
openssl x509 \
-outform der \
-in certificate.pem \
-out certificate.der
```

DER → PEM

```bash
openssl x509 \
-inform der \
-in certificate.der \
-out certificate.pem
```

---

# 11. PKCS#12 (.p12/.pfx)

Create

```bash
openssl pkcs12 \
-export \
-out certificate.p12 \
-inkey private.key \
-in certificate.crt
```

Extract

```bash
openssl pkcs12 \
-in certificate.p12 \
-nodes
```

---

# 12. Encryption & Decryption

Encrypt File

```bash
openssl enc \
-aes-256-cbc \
-in secret.txt \
-out secret.enc
```

Decrypt File

```bash
openssl enc \
-d \
-aes-256-cbc \
-in secret.enc \
-out secret.txt
```

---

# 13. SSL/TLS Testing

Connect

```bash
openssl s_client \
-connect example.com:443
```

Show Certificate

```bash
openssl s_client \
-connect example.com:443 \
-showcerts
```

---

# 14. Verify Certificates

Verify

```bash
openssl verify certificate.crt
```

Verify Against CA

```bash
openssl verify \
-CAfile ca.crt \
certificate.crt
```

---

# 15. Common Problems

Check Key

```bash
openssl rsa \
-check \
-in private.key
```

Verify Certificate Matches Key

```bash
openssl x509 \
-noout \
-modulus \
-in certificate.crt \
| openssl md5

openssl rsa \
-noout \
-modulus \
-in private.key \
| openssl md5
```

---

# 16. Developer Workflow

Generate Private Key

```bash
openssl genrsa -out private.key 4096
```

Create CSR

```bash
openssl req -new \
-key private.key \
-out request.csr
```

Verify Certificate

```bash
openssl verify certificate.crt
```

Check Expiry

```bash
openssl x509 \
-enddate \
-noout \
-in certificate.crt
```

---

# 17. Essential Commands

```bash
openssl version

openssl rand

openssl dgst

openssl genrsa

openssl rsa

openssl req

openssl x509

openssl verify

openssl pkcs12

openssl enc

openssl s_client

openssl base64
```

---

# 18. Best Practices

- Use RSA 4096-bit or modern Elliptic Curve (EC) keys for new deployments.
- Protect private keys with appropriate file permissions (for example, `chmod 600 private.key`).
- Never commit private keys to version control.
- Verify certificates before deploying them.
- Monitor certificate expiration dates and renew them before they expire.
- Use strong encryption algorithms such as AES-256.
- Store CA certificates separately from server certificates.
- Test SSL/TLS configurations using `openssl s_client`.