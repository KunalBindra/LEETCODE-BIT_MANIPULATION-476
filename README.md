# LEETCODE-BIT_MANIPULATION-476
Your code is attempting to find the complement of a number by flipping its bits. However, there's a small issue with your approach. Let's correct and improve it:

```java
class Solution {
    public int findComplement(int num) {
        int mask = (Integer.highestOneBit(num) << 1) - 1;
        return num ^ mask;
    }
}
```

Here's what's changed and why:

1. **Mask Calculation**: `Integer.highestOneBit(num)` finds the highest bit set in `num`. `(highestOneBit(num) << 1) - 1` creates a mask with all bits set up to the highest bit in `num`.

2. **XOR Operation**: `num ^ mask` performs the bitwise XOR operation between `num` and `mask`, effectively flipping all bits of `num` that are set.

This implementation correctly finds the complement of `num` without unnecessary iterations and potential overflow issues that could arise with your original approach using a `long` and bit-shifting within a loop.
