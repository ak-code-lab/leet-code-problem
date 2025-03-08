# Day - 4

## 1. 1952. Three Divisors
```cpp
bool isThree(int n) {
 int count = 0;
 for(int i = 1; i <= n; i++){
 if(n % i == 0) count++;
 }
 return (count == 3) ? 1 : 0;
}
```

## 2. 2427. Number of Common Factors
```cpp
int commonFactors(int a, int b) {
 int count = 0;
 int n = fmin(a,b);
 for(int i=1;i<=n;i++){
 if(a%i==0 && b%i==0) count++;
 }
 return count;
}
```

## 3. 2652. Sum Multiples
```cpp
int sumOfMultiples(int n) {
 int sum = 0;
 for (int i = 1; i <= n; i++) {
 if (i % 3 == 0 || i % 5 == 0 || i % 7 == 0) {
 sum += i;
 }
 }
 return sum;
}
```

## 4. 2739. Total Distance Traveled
```cpp
int distanceTraveled(int mainTank, int additionalTank) {
 int totalDistance = 0;
 while (mainTank > 0) {
 if (mainTank >= 5) {
 mainTank -= 5;
 totalDistance += 50;
 if (additionalTank > 0) {
 mainTank += 1;
 additionalTank -= 1;
 }
 }
else {
 totalDistance += mainTank * 10;
 mainTank = 0;
 }
 }
 return totalDistance;
}
```

## 5. 263. Ugly Number
```cpp
bool isUgly(int n) {
 if(n < 1) return false;
 while(n % 2 == 0 || n % 3 == 0 || n % 5 == 0) {
 if(n % 2 == 0) n /= 2;
 if(n % 3 == 0) n /= 3;
 if(n % 5 == 0) n /= 5;
 }
 return n == 1;
}
```

## 6. 202. Happy Number
```cpp
int getNext(int n) {
 int totalSum = 0;
 while (n > 0) {
 int d = n % 10;
 n = n / 10;
 totalSum += d * d;
 }
 return totalSum;
 }
 bool isHappy(int n) {
 int slowRunner = n;
 int fastRunner = getNext(n);
 while (fastRunner != 1 && slowRunner != fastRunner) {
 slowRunner = getNext(slowRunner);
 fastRunner = getNext(getNext(fastRunner));
 }
 return fastRunner == 1;
}
```

## 7. 231. Power of Two
```cpp
bool isPowerOfTwo(int n) {
 if (n == 0) return false;
 while (n % 2 == 0) n /= 2;
 return n == 1;
}
```

## 8. 326. Power of Three
```cpp
bool isPowerOfThree(int n) {
 if(n < 1) return false;
 if(n == 1) return true;
 while(n % 3 == 0) n /= 3;
 return n==1;
}
```