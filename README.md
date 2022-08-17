# Secure Hashing Algorithm - 256

This is a small scale implementation of the SHA-256 in C++

The program takes in the hexadecimal equivalent of a text and generates its corresponding hash.

# Introduction to Hashing Algorithms

An n-bit hash is a map from arbitrary length messages to n-bit hash values. An n-bit cryptographic hash is an n-bit hash which is one-way and collision-resistant. Such functions are important cryptographic primitives used for such things as digital signatures and password protection.

![image](https://user-images.githubusercontent.com/106404249/185105203-432dd9f8-4071-4182-9035-201c53668ac8.png)

Current popular hashes produce hash values of length n = 128 (MD4 and MD5) and n = 160 (SHA-1), and therefore can provide no more than 64 or 80 bits of
security, respectively, against collision attacks. Since the goal of the new Advanced Encryption Standard (AES) is to offer, at its three cryptovariable sizes, 128, 192, and 256 bits of security, there is a need for companion hash algorithms which provide similar levels of enhanced security.

SHA-256 is a 256-bit hash and is meant to provide 128 bits of security against collision attacks. Similarly, SHA-512 is a 512-bit hash, and is meant to provide 256 bits of security against collision attacks.

# Description of SHA-256

SHA-256 operates in the manner of MD4, MD5, and SHA-1. The message to be hashed is first padded with its length in such a way that the result is a multiple of 512 bits long, and then parsed into 512-bit message blocks.

The SHA-256 compression function operates on a 512-bit message block and a 256-bit intermediate hash value. It is essentially a 256-bit block cipher algorithm which encrypts the intermediate hash value using the message block as key. Hence there are two main components to describe: 
    (1) the SHA-256 compression function, and
    (2) the SHA-256 message schedule

The entire algorithm can be simplified into five steps as follows:
    (1) Padding Bits
    (2) Padding Length
    (3) Initializing the buffers
    (4) Compression Function
    (5) Output generation


The buffer initialisations are:
a. The default values for eight buffers to be used in the rounds as follows
<img width="150" alt="image" src="https://user-images.githubusercontent.com/106404249/185112538-4719b22c-bc39-48fb-8c19-03bd5b6ac677.png">

b. 64 different keys are to be stored in an array, ranging from K[0] to K[63]. They are initialized as follows: 
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/106404249/185112280-d835269b-da4f-49d3-9248-14398463d8f2.png"> 

The compression function details are as follows:
The entire message block that we have ‘n x 512’ bits long is divided into ‘n’ chunks of 512 bits and each of these 512 bits, are then put through 64 rounds of operations and the output obtained is fed as input for the next round of operation.

The value for W(i) at each step is calculated using the following step:
<img width="682" alt="image" src="https://user-images.githubusercontent.com/106404249/185114397-2df52ab1-b6ca-4232-aee1-9c910bcd0eeb.png">

In each round, the following happens and formulas for each of the functions carried out are given below:
![image](https://user-images.githubusercontent.com/106404249/185114588-a6e697d7-969e-445a-a9f4-658284d337cd.png)
<img width="534" alt="image" src="https://user-images.githubusercontent.com/106404249/185115179-c154040d-1eef-4bb1-8f48-f5cf24f8174e.png">

The output from every round acts as an input for the next round and this process keeps on continuing till the last bits of the message remains and the result of the last round for the nᵗʰ part of the message block will give us the result i.e. the hash for the entire message. The length of the output is 256 bits.

# Conclusion
The SHA-256 hashing algorithm is currently one of the most widely used hashing algorithms because it has yet to be cracked and the hashes are calculated faster than other secure hashes such as the SHA-512. It is well established, but the industry is gradually shifting toward the more secure SHA-512, as experts believe SHA-256 will become vulnerable very soon.
