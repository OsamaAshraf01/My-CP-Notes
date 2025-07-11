---
sr-due: 2025-07-12
sr-interval: 1
sr-ease: 230
---

#CPP #review
`memset` is a low-level memory manipulation function in C/C++ that fills a block of memory with a specified byte value. It operates at the **byte level**, meaning it treats memory as a sequence of bytes rather than structured data types (like `int`, `float`, `long double`, etc.).

`memset` fills each byte in the memory block with the **least significant 8 bits** of `value` (since it treats `value` as an `unsigned char`).
- Example:
    - `memset(arr, 0, 100)` → Sets all 100 bytes to `0x00`.   
    - `memset(arr, -1, 100)` → Sets all 100 bytes to `0xFF` (since `-1` in `int` is `0xFFFFFFFF`, but only `0xFF` is used).    
    - `memset(arr, 0xAB, 100)` → Sets all 100 bytes to `0xAB`.  

`memset` **does not know** if the memory is an `int[]`, `float[]`, or `struct`. It blindly writes bytes.


Common cases of `memset`:
1. for `int` -> `0` and `-1`, inf([[How to memset array to infinity]])
2. for `char` -> any char as char is one-byte data type
3. for `double` and `long double` -> only zeros


`memset` fills memory **byte-by-byte**, ignoring data types. It is **safe for zeroing memory** but **unsafe for setting non-zero values in floating-point/object types**. Use `std::fill` or loops instead for correct initialization.
