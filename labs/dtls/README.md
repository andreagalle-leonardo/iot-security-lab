# ECDH Key Exchange Simulation

This lab provides a pure Python simulation of the **Elliptic Curve Diffie-Hellman (ECDH)** protocol.

Instead of running code on hardware, this notebook breaks down the mathematical steps required to establish a secure, encrypted communication channel between two IoT devices (a Sensor and a Gateway) over an insecure network.

## What You Will Learn
* How to generate Elliptic Curve public/private key pairs (NIST P-256).
* How the ECDH "handshake" works mathematically.
* How to derive a symmetric encryption key (AES) from a shared secret point.
* How to encrypt and decrypt actual data strings using the Fernet library.

## 🔐 Security Insights

### Why can't an eavesdropper crack it?
The security relies on the **Elliptic Curve Discrete Logarithm Problem (ECDLP)**. 
An attacker may intercept both **Public Keys**, but calculating the **Shared Secret** requires at least one **Private Key**. Reversing a Public Key to find its Private Key is computationally infeasible with current technology.

### What about "Man-in-the-Middle" (MitM) attacks?
You might wonder: *What if an attacker replaces the public keys with their own during the exchange?*
* **The Limitation:** Pure ECDH provides **confidentiality** but not **authentication**. It ensures no one can read the message, but it doesn't prove *who* you are talking to.
* **The Solution:** In real-world IoT (like DTLS or TLS), ECDH is combined with **Digital Signatures (ECDSA)** or **Certificates**. These mechanisms allow devices to verify each other's identity before or during the key exchange, preventing an attacker from impersonating a legitimate node.

### Implementation Note: Why Fernet?
In this notebook, we use the [**Fernet** library](https://cryptography.io/en/latest/fernet/) to handle the final encryption. While standard AES works with raw bytes, Fernet is used for educational purposes because it automatically handles:
1. **Integrity (HMAC):** Ensuring the encrypted message wasn't modified or tampered with during transit. Even if an attacker cannot read the message, they cannot change its content without being detected.
2. **Initialization Vectors (IV):** Ensuring the same message looks different every time it is encrypted.
3. **Padding:** Managing data blocks to fit the encryption algorithm requirements.

## Run the Simulation

Click the button below to run the notebook in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([ecdh_simulation.ipynb](<https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/andreagalle-leonardo/iot-security-lab/blob/main/labs/dtls/ecdh_simulation.ipynb>))