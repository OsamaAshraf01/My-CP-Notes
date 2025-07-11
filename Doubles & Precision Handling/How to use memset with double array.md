#doubles #flashcards
When you use `memset` to set a `long double` array to `-1`, you are **not setting the floating-point values to `-1.0`**. Instead, you are **writing raw bytes** (`0xFF`) to the memory occupied by the `long double` elements. This leads to **invalid floating-point representations**, resulting in `NaN`.

`memset` works only for `0.0`

To initialize doubles array correctly, you have 3 options:
- using `std::vector`
- initialize using loop
- use `std::fill(arr, arr + size, -1.0)`


revise [[How memset works]]