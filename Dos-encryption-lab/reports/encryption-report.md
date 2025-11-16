# Secure Log Handling — Encryption Report  

**Scope & purpose**  
This document explains how operational logs and notes generated during lab activities were protected using symmetric and asymmetric encryption. The purpose is to demonstrate confidentiality and integrity practices for sharing sensitive investigation data with a Blue Team analyst. All examples below are sanitized and do not include passphrases or private keys.

---

## Files used (example)
- `attacks-log.txt` — sample log containing: attack type, date/time, source/target placeholders (sanitized before committing).  
- `attacks-log.txt.gpg` — example symmetric-encrypted file (do not commit passphrase).  
- `attacks-log.txt.asc` — example file encrypted to an RSA public key (for secure sharing).

> **Important:** Do not commit passphrases, private keys, or sensitive credentials to the repository.

---

## Symmetric encryption (GPG) — high level
**Goal:** Encrypt a log locally using a passphrase so the file remains confidential at rest.

**Typical workflow (safe, no passphrase shown):**
```bash
# Encrypt (symmetric) — you will be prompted for a passphrase (do NOT commit it)
gpg --symmetric --cipher-algo AES256 attacks-log.txt

# Decrypt
gpg --d attacks-log.txt.gpg > attacks-log-decrypted.txt
