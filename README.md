# Password Strength Analyzer (Thiranex Task 1)

A Python tool that evaluates the strength of user-entered passwords, suggests stronger alternatives, and prevents reuse of old passwords.

## Features
- Checks length, complexity (upper/lower/digits/symbols), entropy, sequences, repeats
- Detects common passwords, including leet-speak variants (e.g. `P@ssw0rd`)
- Score out of 100 with rating from VERY WEAK to VERY STRONG
- Suggests stronger alternatives (hardened version, random password, passphrase)
- Optional SQLite database that stores only salted PBKDF2-SHA256 hashes to block password reuse

## Cryptography Concepts Used
- **Entropy:** bits = length x log2(character pool size)
- **Hashing + salting:** passwords are never stored in plain text
- **Key stretching:** PBKDF2 with 200,000 iterations
- **Constant-time comparison:** `hmac.compare_digest`
- **CSPRNG:** `secrets` module for generating passwords

## How to Run
Open `Task1_Thiranex.ipynb` in Google Colab and run the cells in order.
Or run locally: `python password_strength_analyzer.py` (Python 3.8+, no extra libraries).

## Tech Stack
Python, SQLite, hashlib, secrets
