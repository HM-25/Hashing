# Hashing

Study notes on **cryptographic hash functions**: how they work, where they are used in security, and how to identify and work with hashes in practice.

## Contents

| Note | Topic |
|------|-------|
| [Key Terms](Key%20Terms.md) | Plaintext, digest, collision, salt and other core terms |
| [Hash Functions](Hash%20Functions.md) | Properties of hash functions and common algorithms (MD5, SHA family, NTLM, bcrypt) |
| [Uses](Uses.md) | Password storage, integrity checks, digital forensics and malware identification |
| [Automated Hash Recognition and Manual Identification](Automated%20Hash%20Recognition%20and%20Manual%20Identification.md) | Identifying hash types by format, length and prefix, with and without tools |
| [MD5 Collision Demo](MD5%20Collision%20Demo.md) | Why MD5 is broken, shown with a collision example |

## Quick example

```bash
# Compute and verify file hashes
sha256sum file.iso
md5sum file.iso
```

## About

Personal notes written while studying cryptography basics and password security. See also: [CTPH-MAN](https://github.com/HM-25/CTPH-MAN) for fuzzy hashing.
