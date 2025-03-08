

# Day - 5

## 1. 441. Arranging Coins
```cpp
int arrangeCoins(int n) {
 int rows = 0;
 while (n >= rows + 1) {
 rows++;
 n -= rows;
 }
 return rows;
}
```

## 2. 507. Perfect Number
```cpp
bool checkPerfectNumber(int num) {
 int sum = 0;
 for (int i = 1; i <= num / 2; i++) {
 if (num % i == 0) {
 sum += i;
 }
 }
 return sum == num;
}
```

## 3. 172. Factorial Trailing Zeroes
```cpp
int trailingZeroes(int n) {
 int zeroCount = 0;
 while (n > 0) {
 n /= 5;
 zeroCount += n;
 }
 return zeroCount;
}
```

## 4. 3099. Harshad Number
```cpp
int sumOfTheDigitsOfHarshadNumber(int x) {
 int digitSum = 0;
 int temp = x;
 while (temp > 0) {
 digitSum += temp % 10;
 temp /= 10;
 }
 if (x % digitSum == 0) {
 return digitSum;
 }
 return -1;
}
```

## 5. 1518. Water Bottles
```cpp
int numWaterBottles(int numBottles, int numExchange) {
 int res = 0;
 int empty = 0;
 while(numBottles)
 {
 res += numBottles;
 empty += numBottles;
 numBottles = empty/numExchange;
 empty = empty%numExchange;
 }
 return res;
}
```

## 6. 2520. Count the Digits That Divide a Number
```cpp
int countDigits(int num) {
 int originalNum = num;
 int count = 0;
 while (num > 0) {
 int digit = num % 10;
 if (digit != 0 && originalNum % digit == 0) {
 count++;
 }
 num /= 10;
 }
 return count;
}
```

## 7. 2591. Distribute Money to Maximum Children
```cpp
int distMoney(int money, int children) {
 if(money<children) return -1;
 if(money<8) return 0;
 money-=children;
 int count=0;
 while(true)
 {
 if(!children)
 {
 if(!money)return count;
 return count-1;
 }
 if(children!=0 && money>=7)
 {
 if((money-7)!=3)
 {
 children--;
 money-=7;
 count++;
 }
 else if((money-7)==3 && children>2)
 {
 children--;
 money-=7;
 count++;
 }
 else
 {
 return count;
 }
 }
 else
 {
 return count;
 }
 }
 return -1;
}
```

