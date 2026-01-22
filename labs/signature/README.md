# Digital Signatures: ECDSA

In the previous lab, we used Hash functions to verify that data hadn't changed. However, a hash cannot tell you **who** created the data.

This notebook introduces **Digital Signatures** using the **ECDSA (Elliptic Curve Digital Signature Algorithm)** standard. This is the mechanism used by IoT devices to prove their identity and ensure that commands (like "Open Door" or "Update Firmware") actually come from a trusted source and not an attacker.

## What You Will Learn
* **Authenticity:** Proving the origin of a message using Asymmetric Cryptography.
* **The Key Roles:**
    * **Private Key:** Used to *create* the signature (kept secret by the sender).
    * **Public Key:** Used to *verify* the signature (shared with everyone).
* **Attack Simulations:**
    * **Tampering:** See how modifying the message invalidates the signature.
    * **Impersonation:** See how signing with a fake private key fails verification.

## 🔐 Why ECDSA for IoT?

You might have heard of RSA. While RSA is secure, it creates very large keys and signatures.
**ECDSA** is preferred for IoT because it offers the same level of security with much smaller keys (e.g., 256-bit vs 2048-bit), saving battery life and bandwidth on constrained devices.

## Run the Simulation

Click the button below to start the ECDSA simulation in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/andreagalle-leonardo/iot-security-lab/blob/main/labs/signature/ecdsa_simulation.ipynb)