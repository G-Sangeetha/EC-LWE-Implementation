# NA-ECE-Implementation

NA-ECE (Noise-Augmented Elliptic Curve Encryption) is a deterministic noise-augmented elliptic curve encryption scheme designed to enhance ciphertext obfuscation and integrity under classical security assumptions.

This repository provides the reference implementation and benchmarking framework for NA-ECE, including authenticated encryption, ciphertext diversity analysis, and performance evaluation.

The scheme introduces deterministic, curve-valid noise derived from elliptic-curve Diffie–Hellman shared secrets using the RFC 9380 Simplified SWU hash-to-curve mapping. This approach enables increased ciphertext diversity while preserving the compact structure inherent to elliptic-curve encryption.

---

# Repository Structure

### **NA-ECE-Implementation&Testing.ipynb**

The unified notebook containing the complete **NA-ECE implementation and experimental evaluation**.

To ensure deterministic and invertible encoding, the implementation uses **31-byte plaintext blocks**, guaranteeing that each message element interpreted as an integer satisfies **mᵢ < p** for the secp256k1 field modulus.

The notebook includes:

- Standard-compliant deterministic noise generation using the RFC 9380 Simplified SWU mapping  
- Authenticated NA-ECE variant (**Encrypt-then-MAC**) for integrity and malleability resistance  
- Ciphertext diversity and entropy analysis  
- Performance benchmarking across message sizes (**16 to 1024 bytes**)

This notebook serves as the **single source of implementation and experimental results**.

---

### **na_ece_result.csv**

Contains **raw performance data** from **50 independent execution runs** for each message size (16 to 1024 bytes).

This dataset enables:

- statistical reliability analysis  
- runtime variability assessment  
- reproducibility of performance experiments  

---

### **na_ece_result_summary.csv**

Provides the **processed statistical summary (mean values)** for:

- key generation latency
- encryption latency
- decryption latency
- resulting ciphertext sizes

across the evaluated message sizes.

---

# Execution Environment

### **NA-ECE Implementation and Testing**

The notebook **NA-ECE-Implementation&Testing.ipynb** was executed on a local machine with the following configuration:

- **Processor:** Intel i5 (11th Generation)  
- **Memory:** 16 GB RAM  
- **Python Version:** Python 3.x  

This environment was used to evaluate:

- end-to-end NA-ECE encryption and decryption
- ciphertext entropy and uniqueness
- integrity verification and tamper detection
- runtime scalability across increasing message sizes

All performance results reported in the CSV files were generated using this environment.

---

# Usage

### Local Execution

Run the notebook:

`NA-ECE-Implementation&Testing.ipynb`

to:

- execute the full NA-ECE encryption and decryption workflow
- perform ciphertext diversity and entropy experiments
- verify tamper detection and malleability resistance
- generate performance benchmarks automatically saved to:

  `na_ece_result.csv`
  `na_ece_result_summary.csv`


No additional notebooks or scripts are required to reproduce the reported results.

---

# Security Scope

This implementation evaluates **NA-ECE under classical cryptographic assumptions**.

Security relies on:

- elliptic-curve Diffie–Hellman shared secret confidentiality
- cryptographic hash functions modeled as random oracles
- authenticated encryption using the encrypt–then–MAC paradigm

The current implementation **does not provide post-quantum security**, as elliptic-curve discrete logarithms remain vulnerable to quantum algorithms such as Shor’s algorithm.

Future work may explore integration with **post-quantum key establishment mechanisms** for hybrid constructions.

---
