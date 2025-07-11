#CPP

If you use `0xFF` with `memset` on an integer array, each element will be set to `-1`. When you decrement these values sequentially, you’ll observe the following pattern:
- `0xEF`, `0xDF` are small negative values.
- `0xCF` is a moderately small negative number. It can be treated as $-\infty$, with significant headroom. If you define the valid integer range as values greater than it, you can safely add any "valid negative number" without risking overflow — the result will still be $\le -\infty$.
- `0xBF` through `0x9F` are increasingly negative values.
- `0x8F` is the most negative value you'll encounter — it is very close to `LLONG_MIN`.
- `0x7F` is the largest positive number you’ll encounter — it is very close to `LLONG_MAX`.
- `0x6F` through `0x4F` are smaller positive values.
- `0x3F` is a reasonably large positive number and can be considered $+\infty$, with similar headroom. If the valid range is defined as values less than this, adding any "valid positive number" will still yield a result $\ge +\infty$ without overflow.

### Key Takeaways

- If the values are only for reference (i.e., you will **not** perform arithmetic operations on them), use `0x7F` for $+\infty$ and `0x8F` for $-\infty$.
- If you will perform arithmetic (e.g., additions), use `0x3F` for $+\infty$ and `0xCF` for $-\infty$.