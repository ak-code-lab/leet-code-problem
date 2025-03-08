# LeetCode Solutions - Day 8

## 1. 136. Single Number

```c
int singleNumber(int* a, int n) {
    int res = 0;
    for(int i = 0; i < n; i++)
        res = res ^ a[i];
    return res;
}
```

## 2. 268. Missing Number

### Solution 1 (XOR approach)
```c
int missingNumber(int* nums, int n) {
    int missing = n;
    for (int i = 0; i < n; i++) {
        missing ^= i ^ nums[i];
    }
    return missing;
}
```

### Solution 2 (Sum approach)
```c
int missingNumber(int* nums, int n) {
    int sum = n * (n + 1) / 2;
    for (int i = 0; i < n; i++) {
        sum -= nums[i];
    }
    return sum;
}
```

## 3. 1822. Sign of the Product of an Array

```c
int arraySign(int* nums, int numsSize) {
    int negativeCount = 0;
    int zeroCount = 0;
    for (int i = 0; i < numsSize; i++) {
        if (nums[i] == 0) {
            return 0;
        } else if (nums[i] < 0) {
            negativeCount++;
        }
    }
    return (negativeCount % 2 == 0) ? 1 : -1;
}
```

## 4. 2469. Convert the Temperature

```c
double* convertTemperature(double celsius, int* returnSize) {
    static double result[2];
    result[1] = celsius * 9.0 / 5.0 + 32.0;
    result[0] = celsius + 273.15;
    *returnSize = 2;
    return result;
}
```