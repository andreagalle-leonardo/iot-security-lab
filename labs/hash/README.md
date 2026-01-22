# Cryptographic Hash Functions

While encryption hides data, **Hash Functions** are used to prove its **integrity**.

This simulation notebook explores how algorithms like **SHA-256** create unique "digital fingerprints" for data. In an IoT context, hashing is the fundamental building block for **Secure Boot** (ensuring the device runs trusted code) and **OTA Updates** (ensuring downloaded firmware hasn't been corrupted or hacked).

## What You Will Learn
* **The "One-Way" Property:** Understanding why hashes cannot be reversed to reveal the original data.
* **The Avalanche Effect:** Visualizing how changing a single bit of input drastically changes the resulting hash, making even minor tampering obvious.
* **Algorithm Standards:** Comparing the industry-standard **SHA-2** against the newer **SHA-3** (Keccak).
* **Integrity Verification:** A practical simulation of a firmware update process, checking for file corruption or tampering.

## 🔍 Key Concept: Integrity vs. Confidentiality

It is crucial to understand that **hashing is not encryption**.
* **Encryption** turns data into a secret format that can be reversed (decrypted) with a key.
* **Hashing** turns data into a fixed-length string that **cannot** be reversed.

If an attacker modifies a firmware image by even one byte, the hash check will fail, and the IoT device will refuse to install the update. This notebook demonstrates exactly how that mechanism works.


## Run the Simulation

Click the button below to start the Hash simulation in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/andreagalle-leonardo/iot-security-lab/blob/main/labs/hash/hash_simulation.ipynb)
