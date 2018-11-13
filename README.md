# Degree-2-Homomorphic-Paillier

The main idea of this repo is to boost paillier encryption function to support degree-2 homomorphic encryption.(somewhat full homomorphic even though it's only 2-d XD)

## Reference
Catalano, D., & Fiore. (2015). *Using linearly-homomorphic encryption to evaluate degree-2 functions on encrypted data*. Proceedings of the ACM Conference on Computer and Communications Security, 2015, 1518-1529.
[#Avaliable Online#](https://eprint.iacr.org/2014/813.pdf)

The linerly-homomorphic encryption cryptosystem we chose is [Pallier Cryptosystem](https://en.wikipedia.org/wiki/Paillier_cryptosystem#Key_generation). As an addictive homomorphic cryptosystem, when given public key and Enc(m1), Enc(m2), it is possible (in PPT) to calculate Enc(m1+m1). The listed paper presents a method to convert 1-d (linear) homomorphic encryption to 2-d homomorphic encryption. That is to say, we intend to calculate Enc(m1\*m2) without any prior knowledage about m1 and m2. A more concrete formal representation is shown below:

**Enc(m1\*m2-b1\*b2) = Enc((m1-b1)\*(m2-b2))\*Enc(b1)^(m2-b2) \* Enc(b2)^(m1-b1)**

Paillier functions including encryption and decryption function are from [paillier-libraries-benchmarks](https://github.com/snipsco/paillier-libraries-benchmarks) repository.

## Files included
```
Degree-2-Homomorphic-Paillier
+-- src
|	+-- paillier.c
|	+-- paillier_mh.c (core implementation file)
|	+-- test.c (main)
|
+-- include
|	+-- paillier.h
|	+-- paillier_mh.h
|	
+-- README.md
+-- test (binary file)
```
## Prequisite
- [GNU MP Library](https://gmplib.org/), download and install instruction can be found on its official website.

## Install and Run
1. Simply copy the code to your cmomputer (preferred Debian-based), this program has not been tested on other platforms.
2. Run binary file or compile from source file.
`gcc test.c paillier.c paillier_mh.c -o test -lgmp`
