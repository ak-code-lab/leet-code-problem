## LeetCode Solutions

### 1. Add Two Integers (2235)
```cpp
int sum(int num1, int num2) {
    return num1 + num2;
}
```

### 2. A Number After a Double Reversal (2119)
```cpp
bool isSameAfterReversals(int x) {
    return x == 0 || (x % 10 != 0);
}
```

### 3. Minimum Cuts to Divide a Circle (2481)
```cpp
int numberOfCuts(int n) {
    return (n == 1) ? 0 : (n % 2 == 0) ? n / 2 : n;
}
```

### 4. Divisor Game (1025)
```cpp
bool divisorGame(int n) {
    return n % 2 == 0;
}
```

### 5. Nim Game (292)
```cpp
bool canWinNim(int n) {
    return (n % 4 != 0);
}
```

### 6. Add Digits (258)
```cpp
int addDigits(int num) {
    return num == 0 ? 0 : 1 + (num - 1) % 9;
}
```

### 7. Count of Matches in Tournament (1688)
```cpp
int numberOfMatches(int n){
    return n - 1;
}
```

### 8. Smallest Even Multiple (2413)
```cpp
int smallestEvenMultiple(int n) {
    return (n % 2 == 0) ? n : n * 2;
}
