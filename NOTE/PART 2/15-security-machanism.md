# 15. Security Mechanisms

## What are Security Mechanisms?
Security Mechanisms are techniques, methods, and tools used to implement security protections in computer systems, networks, and data.

In simple words:
> **"Security Mechanism = How security protection is provided."**

### Examples
- **Password** → Supports authentication
- **Encryption** → Provides confidentiality
- **Hashing** → Helps verify integrity
- **Digital Signature** → Supports authentication, integrity, and non-repudiation
- **Firewall** → Controls network traffic

---

## Security Service vs Security Mechanism
The easiest way to understand the difference is:
- **Security Service** = *What protection is needed*
- **Security Mechanism** = *How the protection is provided*

### Examples
1. **If we need to keep data confidential:**
   - *Security Service* → Confidentiality
   - *Security Mechanism* → Encryption
2. **If we need to verify a user's identity:**
   - *Security Service* → Authentication
   - *Security Mechanism* → Password + MFA

---

## Why are Security Mechanisms Needed?
Security mechanisms are needed to:
- Protect sensitive information
- Prevent unauthorized access
- Protect data from modification
- Detect suspicious activities
- Control network traffic
- Verify identities
- Recover lost or damaged data
- Support secure communication

---

## Main Security Mechanisms
Important security mechanisms include:
1. Encryption
2. Hashing
3. Digital Signature
4. Authentication Mechanisms
5. Access Control
6. Firewall
7. IDS/IPS
8. Security Auditing and Logging
9. Backup and Recovery

---

## 1. Encryption
Encryption converts readable data, called plaintext, into an unreadable form called ciphertext.

```text
Plaintext → Encryption + Key → Ciphertext
```

Authorized users can decrypt the ciphertext to recover the original data.

```text
Ciphertext → Decryption + Key → Plaintext
```

- **Common Uses:** HTTPS, Online banking, VPN, Secure messaging, File encryption.
- **Main Purpose:** Encryption mainly supports **Confidentiality**.

---

## 2. Hashing
Hashing converts data into a fixed-length value called a hash.

```text
Data → Hash Function → Hash Value
```
The hash can be used to help verify whether data has changed.

- **Common Uses:** Password storage, File integrity checking, Data verification.
- **Example:** `Password → Hash Function → Hash Value`
- **Main Purpose:** Hashing mainly supports **Integrity** and verification.

---

## 3. Digital Signature
A Digital Signature is a cryptographic mechanism used to support **Authenticity**, **Integrity**, and **Non-Repudiation**.

### Basic Process
```text
Document → Digital Signature → Signed Document
```
The receiver can verify the signature to check whether the signed data has been modified and whether the signature matches the expected signer.

- **Common Uses:** Digital contracts, Software signing, Official digital documents, Secure communication.

---

## 4. Authentication Mechanisms
Authentication mechanisms are used to verify the identity of users or devices.

- **Examples:** Password, PIN, OTP, Fingerprint, Face recognition, Security token, Multi-Factor Authentication (MFA).

### MFA Example
```text
Password + OTP → Authentication
```
MFA provides additional protection because it requires more than one authentication factor.

---

## 5. Access Control
Access Control determines which users can access specific resources and what actions they are allowed to perform.

### Example
- **Employee** → Read
- **Manager** → Read + Write
- **Administrator** → Read + Write + Delete

### Common Access Control Elements
- User accounts
- Permissions
- Roles
- Access policies

*Access control helps prevent unauthorized users from accessing or modifying resources.*

---

## 6. Firewall
A Firewall monitors and controls network traffic based on predefined security rules.

```text
Internet → Firewall → Internal Network
```

A firewall can:
- Allow traffic
- Block traffic
- Filter network connections
- Reduce unauthorized access

- **Main Purpose:** Firewalls mainly help with network access control and protection.

---

## 7. IDS and IPS
- **IDS** — Intrusion Detection System
- **IPS** — Intrusion Prevention System

### IDS (Intrusion Detection System)
An IDS monitors activity and detects suspicious behavior.
```text
Network Traffic → IDS → Suspicious Activity → Alert
```

### IPS (Intrusion Prevention System)
An IPS can detect suspicious activity and take action to prevent or block it.
```text
Network Traffic → IPS → Detect Suspicious Activity → Block / Prevent
```

### IDS vs IPS

| Features | IDS | IPS |
| :--- | :--- | :--- |
| **Action** | Detects suspicious activity | Detects and can prevent suspicious activity |
| **Response** | Generates alerts | Can block or stop traffic |
| **Focus** | Mainly detection | Detection + prevention |

---

## 8. Security Auditing and Logging
Logging records important activities occurring in a system or network (e.g., User Login, File Access, Failed Login, System Error, Network Activity).

Security logs can help security teams:
- Monitor activity
- Investigate incidents
- Detect suspicious behavior
- Identify security problems

### Brute Force Detection Example
```text
Failed Login → Failed Login → Failed Login → Failed Login
```
*Multiple failed login attempts may indicate suspicious activity.*

---

## 9. Backup and Recovery
Backup means keeping an additional copy of important data.

```text
Original Data → Backup → Safe Storage
```

If the original data is lost or damaged:
```text
Backup → Recovery → Restored Data
```

- **Useful Against:** Ransomware attacks, Hardware failure, Accidental deletion, Data corruption, System failures.
- **Main Purpose:** Backup and recovery mainly support **Availability** and business continuity.

---

## Security Services and Their Mechanisms

| Security Service | Possible Mechanisms |
| :--- | :--- |
| **Authentication** | Password, OTP, MFA, Biometrics |
| **Confidentiality** | Encryption |
| **Integrity** | Hashing, Digital Signature |
| **Non-Repudiation** | Digital Signature, Audit Logs |
| **Access Control** | Permissions, Roles, Firewall |
| **Availability** | Backup, Recovery, Redundant Systems |

---

## Real-Life Example: Online Banking
An online banking system may use multiple security mechanisms together:

```text
Login → Password + OTP → Authentication → Access Control → HTTPS / Encryption → Secure Transaction → Logging / Audit → Backup & Recovery
```
Different mechanisms provide different layers of protection.

---

## Key Points
- **Security Mechanisms** are methods used to implement security protections.
- **Encryption** protects data confidentiality.
- **Hashing** helps verify data integrity.
- **Digital Signatures** support authenticity, integrity, and non-repudiation.
- **Authentication mechanisms** verify user identity.
- **Access Control** manages permissions.
- **Firewalls** control network traffic.
- **IDS** detects suspicious activity, while **IPS** can block it.
- **Logging** records security-related activities.
- **Backup and Recovery** help restore data after failures or attacks.

---

## Short Summary
Security Mechanisms are the techniques and tools used to provide security services. Common mechanisms include Encryption, Hashing, Digital Signatures, Authentication, Access Control, Firewalls, IDS/IPS, Logging, and Backup/Recovery. Together, they help protect systems, networks, and data from different security threats.
