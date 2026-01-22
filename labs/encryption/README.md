# Symmetric Encryption: AES-CTR

This lab explores the implementation of symmetric encryption, the workhorse of data confidentiality in IoT systems.

Instead of using high-level abstractions, this notebook demonstrates **AES-128 in CTR (Counter) mode** using standard cryptographic primitives. This approach mirrors how encryption is actually handled in low-power operating systems like RIOT OS.

## What You Will Learn
* **Symmetric Key Management:** Using a single shared secret for both encryption and decryption.
* **Stream Cipher Simulation:** How CTR mode transforms a block cipher (AES) into a stream cipher, avoiding the need for data padding.
* **The Role of the Nonce:** Why a "Number Used Once" is critical to prevent identical plaintexts from producing identical ciphertexts.
* **Security Limits:** Practical demonstration of why encryption alone does not guarantee data integrity.

## 🔐 The "Bit-Flipping" Vulnerability

A common misconception is that encrypted data is "tamper-proof." This lab demonstrates why this is false for basic AES modes:

1. **Confidentiality:** An attacker cannot read the message without the secret key.
2. **Lack of Integrity:** In CTR mode, because the encryption is effectively an XOR operation, an attacker can modify specific bits of the ciphertext (**Bit-flipping**).
3. **The Consequence:** The recipient will decrypt the modified ciphertext into a corrupted message without receiving any error or alert.

This illustrates the vital necessity of using **Authenticated Encryption (AEAD)** or **MACs (Message Authentication Codes)** in production IoT environments.

## Run the Simulation

Click the button below to start the AES-CTR simulation in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/andreagalle-leonardo/iot-security-lab/blob/main/labs/encryption/aes_simulation.ipynb)