# Cryptograph

Cryptography means "secret writing" in Greek, more than just secret writing Cryptography can, for example, also be used to prove knowledge of a secret without revealing that secret (e.g., with a digital signature), or to prove the authenticity of data (e.g., with digital fingerprints, also known as "hashes").

## Keys and Addresses
Ownership of ether by EOAs is established through digital private keys,  a private key uniquely determines a single Ethereum address, also known as an account.

Private keys are not used directly in the Ethereum system in any way; they are never transmitted or stored on Ethereum. Access and control of funds is achieved with digital signatures, which are also created using the private key.

### public key cryptography (asymmetric cryptography)
Here keys come in pairs consisting of a private (secret) key and a public key. They are considered a "pair" because the public key is derived from the private key. Together, they represent an Ethereum account.

The private key controls access by being the unique piece of information needed to create digital signatures, which are required to sign transactions to spend any funds in the account. Digital signatures are also used to authenticate owners or users of contracts.

### The magic of public key cryptography
Elliptic curve mathematics means that anyone can verify that a transaction is valid, by checking that the digital signature matches the transaction details and the Ethereum address to which access is being requested. The verification doesn’t involve the private key at all; that remains private. However, the verification process determines beyond doubt that the transaction could have only come from someone with the private key that corresponds to the public key behind the Ethereum address. This is the "magic" of public key cryptography.

There is no encryption as part of the Ethereum protocol—all messages that are sent as part of the operation of the Ethereum network can (necessarily) be read by everyone. As such, private keys are only used to create digital signatures for transaction authentication.


## Private Keys
A private key is simply a number, picked at random. One way to pick your private keys randomly is to simply use a coin, pencil, and paper: toss a coin 256 times and you have the binary digits of a random private key you can use in an Ethereum wallet. The public key and address can then be generated from the private key.

More precisely, a private key can be any nonzero number up to a very large number slightly less than 2<sup>256</sup>a huge 78-digit number, roughly 1.158 * 10<sup>77</sup>. The exact number shares the first 38 digits with 2<sup>256</sup> and is defined as the order of the elliptic curve used in Ethereum.

## Public Keys
An Ethereum public key is a point on an elliptic curve, meaning it is a set of x and y coordinates that satisfy the elliptic curve equation.

## Elliptic Curve Cryptography Explained
Elliptic curve cryptography is a type of asymmetric or public key cryptography based on the discrete logarithm problem as expressed by addition and multiplication on the points of an elliptic curve.

Ethereum uses the exact same elliptic curve, called **secp256k1**, as Bitcoin. That makes it possible to reuse many of the elliptic curve libraries and tools from Bitcoin.

The secp256k1 curve is an elliptic curve that is used in Ethereum. It is defined by the equation y^2 = (x^3 + 7) over a finite field of prime order p, where p is a large prime number. The coordinates (x,y) of a point on this curve can be used for cryptographic operations. To confirm that a point is on the secp256k1 curve, the elliptic curve equation can be used to verify if the coordinates satisfy the equation, which will result in zero if the point is on the curve.

## Elliptic Curve Arithmetic Operations

In summary, elliptic curve arithmetic operations are mathematical operations used in cryptography that are similar to integer arithmetic. The operations include the addition of two points P1 and P2 on the elliptic curve to get a third point P3, and the multiplication of a point P by a whole number k, which is equivalent to repeated addition. The addition operation is defined by drawing a line between P1 and P2 and finding the third point P3 by reflecting the intersection of the line with the curve over the x-axis. The point at infinity serves as the equivalent of zero in normal arithmetic. The addition operation is associative, allowing for the calculation of A + B + C. Multiplication is defined as repeated addition, with k * P = P + P + P +… + P (k times).

## Generating a Public Key

To generate a public key in Ethereum, a private key in the form of a randomly generated number "k" is multiplied by a predetermined point on the curve called the generator point "G". The resulting point is the public key "K". The generator point is always the same for all Ethereum users and is specified in the secp256k1 standard. The relationship between the private key "k" and the public key "K" is fixed and can only be calculated from the private key to the public key. The public key is represented as a serialization of 130 hexadecimal characters and is prefixed with "04" to indicate that it is an uncompressed public key. The serialization concatenates the x and y coordinates of the public key.

## Elliptic Curve Libraries
n cryptocurrency-related projects, there are two main implementations of the secp256k1 elliptic curve: OpenSSL and libsecp256k1. OpenSSL offers a comprehensive set of cryptographic primitives, including secp256k1. The function EC_POINT_mul can be used to derive the public key. On the other hand, libsecp256k1 is a C-language implementation of secp256k1 and other cryptographic primitives that was written from scratch to replace OpenSSL in Bitcoin Core software. It is considered to be superior in performance and security.

## Cryptographic Hash Functions
Cryptographic hash functions are a type of one-way functions used in cryptography for secure data representation and verification. They map data of any size to a fixed-size string of bits. The properties of cryptographic hash functions include determinism, verifiability, noncorrelation, irreversibility, and collision protection. These properties make them useful for various security applications such as data fingerprinting, message integrity, proof of work, authentication, pseudorandom number generators, message commitment, and unique identification. Ethereum uses the Keccak-256 cryptographic hash function, which was a winning algorithm in the SHA-3 Cryptographic Hash Function Competition. However, Ethereum uses the original Keccak algorithm, not the standardized SHA-3, due to controversy over potential NSA influence on the standardization process. To determine if a software library is using Keccak-256 or SHA-3, one can use a test vector, such as an empty input string.

## Ethereum Address Formats
In summary, Ethereum addresses are hexadecimal numbers derived from the public key and are presented without a checksum, unlike Bitcoin addresses which include a built-in checksum. This choice was made with the intention of adding checksums at higher layers, but this caused problems due to slower development of these higher layers. Alternative encodings have been adopted by wallet developers, but more slowly than expected.

## Inter Exchange Client Address Protocol

The Inter Exchange Client Address Protocol (ICAP) is a way of encoding Ethereum addresses that is partially compatible with the International Bank Account Number (IBAN). It is a decentralized, checksummed and interoperable encoding system for Ethereum addresses, and can encode Ethereum addresses or common names registered with an Ethereum name registry. ICAP uses the same structure as IBAN with a non-standard country code "XE" for Ethereum and a two-character checksum. It has three variations for encoding an account identifier: Direct, Basic and Indirect. Direct encoding can encode Ethereum addresses that start with zero bytes, but is limited to 33 characters. Basic encoding can encode any Ethereum address but is 35 characters long and incompatible with IBAN format. Indirect encoding uses a name registry provider to resolve an identifier to an Ethereum address. The "helpeth" command line tool can be used to create ICAP addresses. Currently, ICAP is only supported by a few wallets.

## Hex Encoding with Checksum in Capitalization (EIP-55)

Ethereum Improvement Proposal 55 (EIP-55) proposed a standard for Ethereum addresses by modifying the capitalization of the hexadecimal address to provide a backward-compatible checksum. This helps in protecting the integrity of the address against typing or reading errors. Wallets that support EIP-55 can validate the address with 99.986% accuracy. The mixed-capitals encoding is generated by taking the Keccak-256 hash of the lowercase hexadecimal address and encoding it in the capitalization of the address. The alphabetic characters in the address are capitalized if the corresponding hex digit of the hash is greater than or equal to 0x8. If an error is detected in the address, the wallet will convert it to lowercase, calculate the checksum hash, and compare it to the original hash. If there is a difference, it means an error has been made in reading or typing the address.

## Conclusions
In this chapter we provided a brief survey of public key cryptography and focused on the use of public and private keys in Ethereum and the use of cryptographic tools, such as hash functions, in the creation and verification of Ethereum addresses. We also looked at digital signatures and how they can demonstrate ownership of a private key without revealing that private key. In [wallets_chapter], we will put these ideas together and look at how wallets can be used to manage collections of keys.


