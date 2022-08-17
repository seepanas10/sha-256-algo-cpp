# Secure Hashing Algorithm - 256

This is a small scale implementation of the SHA-256 in C++

The program takes in the hexadecimal equivalent of a text and generates its corresponding hash.

# Introduction to Hashing Algorithms

An n-bit hash is a map from arbitrary length messages to n-bit hash values. An n-bit cryptographic hash is an n-bit hash which is one-way and collision-resistant. Such functions are important cryptographic primitives used for such things as digital signatures and password protection.

Current popular hashes produce hash values of length n = 128 (MD4 and MD5) and n = 160 (SHA-1), and therefore can provide no more than 64 or 80 bits of
security, respectively, against collision attacks. Since the goal of the new Advanced Encryption Standard (AES) is to offer, at its three cryptovariable sizes, 128, 192, and 256 bits of security, there is a need for companion hash algorithms which provide similar levels of enhanced security.

SHA-256 is a 256-bit hash and is meant to provide 128 bits of security against collision attacks. Similarly, SHA-512 is a 512-bit hash, and is meant to provide 256 bits of security against collision attacks.




