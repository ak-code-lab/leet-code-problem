#### 1. Reverse Integer (7)
```cpp
int reverse(int x){
    long rev = 0;
    while (x != 0) {
        rev = rev * 10 + x % 10;
        x /= 10;
    }
    if (rev > INT_MAX || rev < INT_MIN) {
        return 0;
    }
    return rev;
}
```

#### 2. Palindrome Number (9)
```cpp
bool isPalindrome(int x) {
    if (x < 0 || (x % 10 == 0 && x != 0)) return false;
    int rev = 0;
    while (x > rev) {
        rev = rev * 10 + x % 10;
        x /= 10;
    }
    return x == rev || x == rev / 10;
}
```

#### 3. Fibonacci Number (509)
```cpp
int fib(int N){
    if (N <= 1) {
        return N;
    }
    int current = 0;
    int prev1 = 1;
    int prev2 = 0;
    for (int i = 2; i <= N; i++) {
        current = prev1 + prev2;
        prev2 = prev1;
        prev1 = current;
    }
    return current;
}
```

#### 4. N-th Tribonacci Number (1137)
```cpp
int tribonacci(int n) {
    if (n == 0) return 0;
    if (n <= 2) return 1;
    int a = 0, b = 1, c = 1, current;
    for (int i = 3; i <= n; i++) {
        current = a + b + c;
        a = b;
        b = c;
        c = current;
    }
    return c;
}
```

#### 5. Subtract the Product and Sum of Digits of an Integer (1281)
```cpp
int subtractProductAndSum(int n) {
    int product = 1;
    int sum = 0;
    while (n > 0) {
        int digit = n % 10;
        product *= digit;
        sum += digit;
        n /= 10;
    }
    return product - sum;
}
```

#### 6. Number of Steps to Reduce a Number to Zero (1342)
```cpp
int numberOfSteps(int num) {
    int steps = 0;
    while (num) {
        num = num % 2 ? num - 1 : num / 2;
        steps++;
    }
    return steps;
}
```