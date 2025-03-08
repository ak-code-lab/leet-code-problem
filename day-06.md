
## Day - 6

### 1. Count Odd Numbers in an Interval Range (1523)
```cpp
int countOdds(int low, int high) {
    if((low&1)==0) low++;
    return low > high ? 0 : (high - low) / 2 + 1;
}
```

### 2. Power of Two (231)
```cpp
bool isPowerOfTwo(int x) {
    long n = x;
    if(n && (n & n - 1) == 0)
        return true;
    else
        return false;
}
```

### 3. Power of Four (342)
```cpp
int isPowerOfFour(int n) {
    if(n > 0 && (n & n - 1) == 0 && (n % 3 == 1))
        return 1;
    return 0;
}
```

### 4. Number of 1 Bits (191)
```cpp
int hammingWeight(int n) {
    int sum = 0;
    while (n != 0) {
        sum++;
        n = n & (n - 1);
    }
    return sum;
}
```

### 5. Hamming Distance (461)
```cpp
int hammingDistance(int x, int y) {
    int xor = x ^ y;
    int distance = 0;
    while (xor != 0) {
        distance += 1;
        xor = xor & (xor - 1);
    }
    return distance;
}
```

### 6. Binary Number with Alternating Bits (693)
```cpp
bool hasAlternatingBits(int n) {
    return (n & (n >> 1)) == 0 && (n & (n >> 2)) == (n >> 2);
}
```