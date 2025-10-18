# SHA-256 Hash Generator (C++ Implementation)
###  Compute the SHA-256 Hash of the Book of Mark (RSV)

This project provides a **pure C++17 implementation** of the SHA-256 algorithm and demonstrates its use by computing the hash of the *Book of Mark* (from the Revised Standard Version Bible).

The implementation follows the official pseudocode from the [SHA-2 standard (FIPS PUB 180-4)](https://csrc.nist.gov/publications/detail/fips/180/4/final) and [Wikipedia’s SHA-2 article](https://en.wikipedia.org/wiki/SHA-2).

---

##  Project Overview

**Files:**
- `sha256_mark.cpp` → Full C++ source code implementing SHA-256
- `mark_rsv.txt` → Input file containing the Book of Mark text
- `README.md` → Documentation and usage guide

**Output:**  
A 64-character hexadecimal SHA-256 hash representing the contents of the Book of Mark text.

---

##  How SHA-256 Works

SHA-256 (Secure Hash Algorithm 256-bit) produces a unique 256-bit (32-byte) message digest for any input data.  
It’s a one-way cryptographic function widely used in:
- Digital signatures
- Password hashing
- Data integrity verification
- Blockchain technology

**Main Steps:**
1. **Preprocessing:** Pads the input to a multiple of 512 bits.
2. **Parsing:** Divides message into 512-bit blocks.
3. **Message Schedule:** Expands 16 words into 64.
4. **Compression:** Performs 64 rounds of bitwise operations and modular additions.
5. **Finalization:** Combines internal states into a 256-bit digest.

---

##  Code Features

Fully self-contained — no external libraries  
 Implements all core SHA-256 bitwise operations  
 Works on any text or binary input  
 Tested against standard vectors (e.g., `"abc"`)  
 Compatible with C++17 or later  

---

## Example Code Structure

| Function | Description |
|-----------|--------------|
| `rotr(x, n)` | Performs right rotation on a 32-bit word. |
| `choose(e, f, g)` | SHA-256 choice function. |
| `majority(a, b, c)` | SHA-256 majority function. |
| `sig0(x)`, `sig1(x)` | Bitwise sigma functions for word expansion. |
| `transform()` | Core 64-round compression function. |
| `update()` | Feeds message data into the buffer. |
| `final()` | Pads, finalizes, and returns the hash. |

---

##  Usage Guide

### 1️ Prerequisites
You need any C++17-compatible compiler:
- GCC 9+  
- Clang 10+  
- MSVC 2019+  

---

### 2️ Clone or Download

```bash
git clone https://github.com/<your-username>/sha256-mark.git
cd sha256-mark
