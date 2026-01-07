# EC-LWE-Implementation
Implementation and benchmarking of the Noise-Augmented Elliptic-Curve Learning With Errors (EC-LWE) scheme.

**Repository Structure**

**EC_LWE_test.ipynb:** The core implementation of the EC-LWE protocol, including RFC 9380 hash-to-curve noise generation and entropy testing. (Runs on Local Machine).

**Test_on_ECC&PQC.ipynb:** Google Colab notebook containing the comparative benchmarking against ECC, NTRU, Kyber and FrodoKEM.

**ec_lwe_result.csv:** Contains raw performance data from 50 independent execution runs for each message size (16 to 1024 bytes). This file provides the basis for our statistical reliability and outlier analysis.

**ec_lwe_result_summary.csv:** Provides the processed statistical summary (Mean and Standard Deviation) for key generation, encryption, and decryption latencies, as well as final ciphertext sizes across the tested message range.

**Usage**

**Local Test:** Run EC_LWE_test.ipynb to generate the performance metrics and entropy scores for the EC-LWE scheme.

**Cloud Benchmarking:** Open Test_on_ECC&PQC.ipynb in Google Colab, upload the required libraries, and run all cells to reproduce the NIST PQC comparison results.
