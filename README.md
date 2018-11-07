# 5-Round-AES-Distinguisher

## 8bit AES Distinguisher
compile with:
g++ -maes -march=native -msse -msse2 main.cpp -o <output-file>

run by calling ./output-file

RANDOM_PERMUTATION 1 to use 12 rounds AES, effectively random permutation
RANDOM_PERMUTATION 0 to use 5 rounds AES

BUFFER_SIZE controls size of small buffer in Number of diagonals for results before writing to array. must be divisor of 2^32 (example BUFFER_SIZE 32 creates a buffer of size 32 * sizeof(uint64_t)

SAMPLES controls number of samples to compute (example SAMPLES 256 computes 256 samples)

INTER_RES controls number of results after which an intermediary result is written to file (example INTER_RES 4 causes an intermediary result after every 4 samples)

## 6bit AES Distinguisher
compile with:
g++ -lpthread aes.cpp 

run by calling ./output-file number-of-cosets number-of-threads

Options:
in aes6bit.h
Nr defines the number of rounds of AES to compute. Nr 5 to use distinguisher Nr 12+ to use as random permutation
AES_keyExpSize defines size of expanded key

in cosets.cpp
USE_C_RNG 1 to use std::random for RNG
USE_C_RNG 0 to use Mersenne Twister for RNG

