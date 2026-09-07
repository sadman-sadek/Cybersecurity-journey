# 14. Security Services

## What are Security Services?
Security Services are security functions that protect computer systems, networks, and data from unauthorized access, modification, disclosure, and other attacks.

In simple words:
> **"Security Services provide different types of protection to keep systems and data secure."**

---

## Why are Security Services Needed?
Security services are needed to:
- Protect sensitive information
- Prevent unauthorized access
- Keep data private
- Prevent unauthorized data modification
- Verify user identities
- Provide proof of actions or transactions
- Protect systems from different security threats

---

## Main Security Services
The main security services are:
1. Authentication
2. Access Control
3. Data Confidentiality
4. Data Integrity
5. Non-Repudiation

---

## 1. Authentication
Authentication is the process of verifying the identity of a user, device, or system. It answers the question: **"Who are you?"**

### Examples
- Username and password
- PIN / OTP
- Fingerprint / Face recognition
- Security tokens

### Basic Process
```text
User
  ↓
Username + Password
  ↓
Authentication
  ↓
Identity Verified
  ↓
Access Granted
```

---

## 2. Access Control
Access Control determines what an authenticated user is allowed to access or perform. It answers the question: **"What are you allowed to do?"**

### Example
- **Employee** → Read files
- **Manager** → Read + Edit files
- **Administrator** → Full access

### Authentication vs Access Control

| Authentication | Access Control |
| :--- | :--- |
| Verifies identity | Determines permissions |
| Answers "Who are you?" | Answers "What can you do?" |
| Related to login | Related to authorization |

---

## 3. Data Confidentiality
Confidentiality ensures that sensitive data can only be accessed by authorized users. Encryption is one of the most important mechanisms used to provide confidentiality.

### Example
```text
Plaintext → Encryption → Ciphertext → Network → Decryption → Plaintext
```

### Examples of Use
- Online banking
- HTTPS websites
- Private messages
- Confidential business files

> 🔒 *Confidentiality protects data from unauthorized disclosure.*

---

## 4. Data Integrity
Data Integrity ensures that data is not changed, modified, or deleted by unauthorized users.

### Example
*   **Original data:** `Account Balance = $500`
*   **Violated Integrity:** If an attacker changes it to `Account Balance = $5000`.

### Common Mechanisms
- Hashing
- Digital signatures
- Checksums
- Message Authentication Codes (MAC)

---

## 5. Non-Repudiation
Non-Repudiation provides evidence that a particular user performed an action or sent a message, making it difficult for that user to later deny the action. Digital signatures are commonly used to support non-repudiation.

### Example
Suppose a person digitally signs an electronic contract. Later, the person claims: *"I did not sign this document."* 
A valid digital signature can provide cryptographic evidence associated with the signer and the signed data.

### Common Uses
- Digital contracts
- Electronic transactions
- Official digital documents
- Secure communications

---

## How Security Services Work Together
A secure online banking system may use several security services together:

```text
User
 ↓
Authentication
 ↓
Access Control
 ↓
Confidentiality
 ↓
Integrity
 ↓
Non-Repudiation
 ↓
Secure Transaction
```

1. **Authentication:** Verifies the user's identity.
2. **Access Control:** Determines what the user can do.
3. **Confidentiality:** Protects sensitive data from unauthorized disclosure.
4. **Integrity:** Protects data from unauthorized modification.
5. **Non-Repudiation:** Provides evidence of important actions or transactions.

---

## Security Services vs Security Mechanisms
These two concepts are related but different.

- **Security Service:** Describes **what** security protection is needed.
  * *Examples:* Authentication, Confidentiality, Integrity
- **Security Mechanism:** Describes **how** the security protection is implemented.
  * *Examples:* Password, Encryption, Hashing, Digital Signature, Firewall

> 💡 **In simple terms:**
> *   *"Security Service = What we want"*
> *   *"Security Mechanism = How we achieve it"*

---

## Real-Life Example
Consider an online email or banking system:

| Security Service | Example / Mechanism |
| :--- | :--- |
| **Authentication** | Password + MFA |
| **Access Control** | User permissions (Read/Write) |
| **Confidentiality** | Encryption / HTTPS |
| **Integrity** | Hashing / cryptographic verification |
| **Non-Repudiation** | Digital signatures where applicable |

---

## Key Points
- **Authentication** verifies identity.
- **Access Control** determines permissions.
- **Confidentiality** keeps data private.
- **Integrity** protects data from unauthorized modification.
- **Non-Repudiation** provides evidence of an action or transaction.
- **Security services** describe *what* protection is required.
- **Security mechanisms** describe *how* that protection is provided.

---

## Short Summary
Security Services are functions that protect systems, networks, and data from security threats. The major services include Authentication, Access Control, Confidentiality, Integrity, and Non-Repudiation. These services work together to provide secure and reliable communication and system operations.
