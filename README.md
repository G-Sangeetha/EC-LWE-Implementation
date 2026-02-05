# EC-LWE-Implementation
Implementation and benchmarking of the Noise-Augmented Elliptic-Curve Learning With Errors (EC-LWE) scheme under classical security assumptions, including authenticated encryption, ciphertext diversity analysis, and performance evaluation.

**Repository Structure**

**EC-LWE-Implementation&Testing.ipynb:** 
The unified and final notebook containing the complete EC-LWE implementation and evaluation, including:

RFC 9380 hash-to-curve–based deterministic noise generation

Authenticated EC-LWE variant (encrypt-then-MAC) for integrity and malleability resistance

Ciphertext diversity and entropy analysis

Performance benchmarking across message sizes (16 to 1024 bytes)

This notebook is the single source of implementation and results.

**ec_lwe_result.csv:** Contains raw performance data from 50 independent execution runs for each message size (16 to 1024 bytes). This file provides the basis for statistical reliability and variability analysis.

**ec_lwe_result_summary.csv:** Provides the processed statistical summary (mean values) for key generation, encryption, and decryption latencies, along with final ciphertext sizes across the tested message range.

**Execution Environments**

**EC-LWE Implementation and Testing (EC-LWE-Implementation&Testing.ipynb):** Executed on a local machine [Intel i5, 11th Gen, 16 GB RAM] to evaluate:

End-to-end performance

Ciphertext entropy and uniqueness

Integrity and tamper-detection behavior

Practical scaling characteristics under a consistent classical threat model

All reported results in the accompanying CSV files were generated using this environment.

**Usage**

**Local Execution:** Run EC-LWE-Implementation&Testing.ipynb to:

Execute the full EC-LWE encryption and decryption workflow

Perform ciphertext diversity and entropy tests

Verify malleability resistance via tampering detection

Generate performance results automatically saved to

ec_lwe_result.csv

ec_lwe_result_summary.csv

No additional notebooks are required to reproduce the reported results.

**Note:** This implementation is evaluated under classical security assumptions. Post-quantum key establishment is not addressed in the current version.
