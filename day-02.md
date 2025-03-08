
#### 1. Calculate Delayed Arrival Time (2651)
```cpp
int findDelayedArrivalTime(int arrivalTime, int delayedTime) {
    return (arrivalTime + delayedTime) % 24;
}
```

#### 2. Find the Pivot Integer (2485)
```cpp
int pivotInteger(int n) {
    int sum = n * (n + 1) / 2;
    int pivot = sqrt(sum);
    return (pivot * pivot == sum) ? pivot : -1;
}
```

#### 3. K Items With the Maximum Sum (2600)
```cpp
int kItemsWithMaximumSum(int numOnes, int numZeros, int numNegOnes, int k) {
    return (k <= numOnes) ? k :
           (k <= numOnes + numZeros) ? numOnes :
           numOnes - (k - numOnes - numZeros);
}
```

#### 4. Count Distinct Numbers on Board (2549)
```cpp
int distinctIntegers(int n) {
    return (n == 1) ? 1 : n - 1;
}
```

#### 5. Find the Maximum Achievable Number (2769)
```cpp
int theMaximumAchievableX(int num, int t) {
    return num + t * 2;
}
```

#### 6. Account Balance After Rounded Purchase (2806)
```cpp
int accountBalanceAfterPurchase(int purchaseAmount) {
    int initialBalance = 100;
    int roundedAmount = ((purchaseAmount + 5) / 10) * 10;
    int finalBalance = initialBalance - roundedAmount;
    return finalBalance;
}
```

#### 7. Pass the Pillow (2582)
```cpp
int passThePillow(int n, int time) {
    int pos = time % (2 * (n - 1));
    return (pos < n) ? (pos + 1) : (2 * n - pos - 1);
}
```

#### Extra: Find the Child Who Has the Ball After K Seconds (3178)
```cpp
int numberOfChild(int n, int k) {
    int pos = k % (2 * (n - 1));
    return pos < n ? pos : 2 * (n - 1) - pos;
}