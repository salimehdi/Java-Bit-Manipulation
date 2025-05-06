## 1. Check Even/Odd

```java
boolean isOdd(int x) {
    return (x & 1) == 1;
}
boolean isEven(int x) {
    return (x & 1) == 0;
}
```

---

## 2. Multiply/Divide by 2

```java
int timesTwo(int x) {
    return x << 1;   // = x * 2
}
int half(int x) {
    return x >> 1;   // = floor(x / 2)
}
```

---

## 3. Swap Two Integers Without a Temp

```java
void swap(int a, int b) {
    a ^= b;
    b ^= a;
    a ^= b;
    // now a and b are swapped
}
```

---

## 4. Get/Set/Clear/Toggle the kᵗʰ Bit

```java
// Get kᵗʰ bit (0-indexed)
int getBit(int n, int k) {
    return (n >> k) & 1;
}
// Set kᵗʰ bit
int setBit(int n, int k) {
    return n | (1 << k);
}
// Clear kᵗʰ bit
int clearBit(int n, int k) {
    return n & ~(1 << k);
}
// Toggle kᵗʰ bit
int toggleBit(int n, int k) {
    return n ^ (1 << k);
}
```

---

## 5. Clear Lowest Set Bit

```java
// Drops the lowest-order 1 bit to 0
int clearLowestSetBit(int n) {
    return n & (n - 1);
}
```

---

## 6. Check Power of Two

```java
boolean isPowerOfTwo(int n) {
    return n > 0 && (n & (n - 1)) == 0;
}
```

---

## 7. Count Set Bits (Brian Kernighan’s Algorithm)

```java
int countSetBits(int n) {
    int count = 0;
    while (n != 0) {
        n &= (n - 1);  // clear lowest set bit
        count++;
    }
    return count;
}
```

---

## 8. Isolate Lowest Set Bit

```java
// e.g. for n=10 (1010₂), returns 0010₂ = 2
int isolateLowestSetBit(int n) {
    return n & -n;
}
```

---

## 9. Find Non-Duplicate Element in an Array

```java
int findSingle(int[] arr) {
    int result = 0;
    for (int x : arr) {
        result ^= x;
    }
    return result;
}
```

---

## 10. Modulo with Power of Two

```java
// n % m where m is power of two: faster than % operator
int modPow2(int n, int m) {
    return n & (m - 1);
}
```

---

## 11. Add Two Numbers Without ‘+’

```java
int add(int a, int b) {
    while (b != 0) {
        int carry = (a & b) << 1;
        a = a ^ b;
        b = carry;
    }
    return a;
}
```

---

## 12. Compute Absolute Value

```java
int abs(int x) {
    int mask = x >> 31;          // all 1’s if x<0, else all 0’s
    return (x ^ mask) - mask;
}
```

---

## 13. Compute Floor(log₂ n)

```java
int floorLog2(int n) {
    return 31 - Integer.numberOfLeadingZeros(n);
}
```

---

## 14. Round Up to Next Power of Two

```java
int nextPowerOfTwo(int n) {
    n--;
    n |= n >> 1;
    n |= n >> 2;
    n |= n >> 4;
    n |= n >> 8;
    n |= n >> 16;
    return n + 1;
}
```

---

## 15. Convert to Gray Code and Back

```java
// Binary → Gray
int toGray(int n) {
    return n ^ (n >> 1);
}
// Gray → Binary
int grayToBinary(int g) {
    int b = 0;
    for (; g != 0; g >>= 1) {
        b ^= g;
    }
    return b;
}
```

---

## 16. Swap Two Bits at Positions i and j

```java
int swapBits(int n, int i, int j) {
    // Only swap if bits differ
    if (((n >> i) & 1) != ((n >> j) & 1)) {
        int mask = (1 << i) | (1 << j);
        n ^= mask;
    }
    return n;
}
```

---

If this helped you so please don't forget to leave a star !
