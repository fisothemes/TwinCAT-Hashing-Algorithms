# TwinCAT Hashing Algorithms

A library containing the most commonly used non-cryptographic hashing functions such as [MurmurHash3](https://en.wikipedia.org/wiki/MurmurHash), [CRC32](https://lxp32.github.io/docs/a-simple-example-crc32-calculation/) and [FNV1a](https://en.wikipedia.org/wiki/Fowler%E2%80%93Noll%E2%80%93Vo_hash_function). All functions Hash data of type [ANY](https://infosys.beckhoff.com/content/1033/tc3_plc_intro/2529426571.html).

# Table of Contents
* Functions
    * [F_CRC32](#f_crc32)
    * [F_DJB2](#f_djb2)
    * [F_FNV1a](#f_fnv1a)
    * [F_Lose_Lose](#f_lose_lose)
    * [F_MurMurHash3](#f_murmurhash3)
    * [F_SDBM](#f_sdbm)
    * [F_Hash_Code](#f_hash_code)
* [Developer Notes](#developer-notes)

# F_CRC32
**Signature:**
```Pascal
FUNCTION F_CRC32 : DWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : DWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_CRC32(sData); // Output: 3421780262
nDINT_Hash      := F_CRC32(nData); // Output: 417295518
```
**Source:** https://lxp32.github.io/docs/a-simple-example-crc32-calculation/


# F_DJB2
**Signature:**
```Pascal
FUNCTION F_DJB2 : DWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : DWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_DJB2(sData); // Output: 902675330
nDINT_Hash      := F_DJB2(nData); // Output: 2087454537
```
**Source:** http://www.cse.yorku.ca/~oz/hash.html


# F_FNV1a
**Signature:**
```Pascal
FUNCTION F_FNV1a : DWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : DWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_FNV1a(sData); // Output: 3146166556
nDINT_Hash      := F_FNV1a(nData); // Output: 1186151337
```
**Source:** http://www.isthe.com/chongo/tech/comp/fnv/


# F_Lose_Lose
**Signature:**
```Pascal
FUNCTION F_Lose_Lose : DWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : DWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_Lose_Lose(sData); // Output: 477
nDINT_Hash      := F_Lose_Lose(nData); // Output: 324
```
**Source:** http://www.cse.yorku.ca/~oz/hash.html


# F_MurMurHash3
**Signature:**
```Pascal
FUNCTION F_MurMurHash3 : DWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : DWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_MurMurHash3(sData); // Output: 3036607362
nDINT_Hash      := F_MurMurHash3(nData); // Output: 3206620847
```
**Source:** https://en.wikipedia.org/wiki/MurmurHash

# F_SDBM
**Signature:**
```Pascal
FUNCTION F_SDBM : DWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : DWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_SDBM(sData); // Output: 1755344949
nDINT_Hash      := F_SDBM(nData); // Output: 912040036
```
**Source:** http://www.cse.yorku.ca/~oz/hash.html

# F_Hash_Code
**Description:**

64-bit hash code generated using MurmurHash3 and FNV1a hashing algorithms. Hash code is different for each runtime to mitigate [hash flooding](https://en.wikipedia.org/wiki/Collision_attack#:~:text=certificates.%5B14%5D-,Hash%20flooding,-%5Bedit%5D).

**Signature:**
```Pascal
FUNCTION F_Hash_Code : LWORD
VAR_INPUT
	Data : ANY;
END_VAR
```
## Example
**Declarations:** 
```Pascal
sData        : STRING  := '123456789';
nData        : DINT    := 123456789;
nSTRING_Hash,
nDINT_Hash   : LWORD;
```
**Implementation:**
```Pascal
nSTRING_Hash    := F_Hash_Code(sData); // Output: See description
nDINT_Hash      := F_Hash_Code(nData); // Output: See description
```

# Developer Notes
TBD
