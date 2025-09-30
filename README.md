# Day_6_Password_Evaluation
# Password Evaluation Report

## Overview

This document summarizes the evaluation of the password **`1q3s5z6k8ug654`** using *The Password Meter* (v.2.0). The meter produced a **100%** score and classified the password as **Very Strong**. Below are the key findings, practical tips, a short primer on common password attacks, and a summary of how password complexity affects security.

---

## Meter Breakdown (short summary)

* **Length:** 14 characters → significant bonus.
* **Lowercase letters:** 6 occurrences → bonus.
* **Numbers:** 8 occurrences → bonus.
* **Middle numbers or symbols:** 6 occurrences → bonus.
* **Repeat characters (case insensitive):** small deduction.
* **Consecutive lowercase letters & consecutive numbers:** small deductions.
* **Sequential numbers (3+):** small deduction.

> Final score: **100 / 100** (Very Strong)

---

## Tips Learned from the Evaluation

1. **Length is extremely important.** Adding characters gives a strong flat bonus; long passphrases are hard to attack.
2. **Use mixed character classes.** Combining lowercase, uppercase, numbers, and symbols yields additional bonuses.
3. **Place numbers/symbols in the middle.** The meter rewards middle numbers/symbols (they add to entropy in practice).
4. **Avoid obvious sequences and repeats.** Sequential characters (e.g., `1234`, `abcd`) and repeated characters reduce score.
5. **Mix cases where practical.** Uppercase letters are rewarded when used among other characters (avoid all-lowercase).
6. **Prefer randomness or long passphrases over predictable substitutions.** `P@ssw0rd` is still weak despite symbol substitution.
7. **Meet multiple requirements.** Tools often apply extra bonuses when you satisfy a variety of conditions (length + multiple character classes).
8. **Use unique passwords per account.** Strength is wasted if re-used across multiple services that might be breached.
9. **Use a password manager.** It helps create, store, and autofill long, unique, and random passwords.

---

## Common Password Attacks (short research)

### Brute Force

An attacker attempts every possible combination of characters until the correct password is discovered. Time-to-crack grows exponentially with length and character-set size. Long passwords and passphrases drastically increase the time required.

### Dictionary Attack

An attacker tries passwords from a precompiled list of common words, phrases, and leaked passwords (often including common substitutions). Simple dictionary words or single-word passwords are highly vulnerable.

### Credential Stuffing

Attackers reuse username/password pairs obtained from previous breaches to try logins on other services. Reused passwords across sites are the enabling factor.

### Rainbow Tables

Precomputed tables of plaintext password ↔ hash mappings can speed up cracking of hashed passwords (unless salts are used). Modern systems use salts and slow hash functions (e.g., bcrypt, Argon2) to mitigate this.

### Social Engineering / Phishing

Attackers trick users into revealing credentials directly (phishing pages, phone scams). No amount of password complexity helps if the password is willingly given away.

### Keylogging & Malware

Malware can capture keystrokes or exfiltrate stored credentials. Device security and careful browsing habits are important complements to password complexity.

---

## How Password Complexity Affects Security

* **Character set (variety):** Increasing the number of allowed character types (lowercase, uppercase, digits, symbols) increases the number of possible combinations per character, raising the search space.
* **Length:** Each additional character multiplies the total search space. Practically, length provides the largest single improvement to estimated cracking time.
* **Entropy distribution:** A long password composed of predictable patterns (e.g., `Password123456`) has less entropy than a random-looking passphrase of similar length.
* **Practical considerations:** Attackers typically try dictionary words, common substitutions, and leaked lists first — so avoiding dictionary words and common patterns is more effective than adding a single symbol.
* **Defensive layering:** Password complexity is necessary but not sufficient. Proper defenses include per-account unique passwords, multi-factor authentication (MFA), slow salted hashing on the server, rate-limiting, and monitoring for credential-stuffing attempts.

---

## Recommendations & Best Practices

1. **Use passphrases:** Aim for 16+ characters where possible (a few random words or a sentence-like phrase).
2. **Mix character classes:** Include lowercase, uppercase, numbers, and symbols, but prioritize length and unpredictability.
3. **Avoid patterns & sequences:** No `1234`, `abcd`, repeated characters, or common keyboard sequences.
4. **Unique passwords:** Use a different password for every important account—particularly email, financial, and admin accounts.
5. **Use a password manager:** Generate and store long random passwords; you only need to remember one strong master password.
6. **Enable MFA:** Wherever available, enable multi-factor authentication (TOTP, hardware token) to mitigate password-only compromise.
7. **Keep devices & software updated:** Protect against malware that could capture typed passwords.
8. **Use modern hashing & salting server-side:** If you manage authentication systems, employ Argon2/bcrypt/scrypt with unique salts and rate limiting.

---

## Further Reading

* NIST Digital Identity Guidelines (SP 800-63B) — recommendations on memorized secrets and authentication.
* OWASP Authentication Cheat Sheet — practical guidance for implementing secure authentication.

---
