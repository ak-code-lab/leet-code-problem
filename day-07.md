
## Day - 7

### 1. Min Cost to Move Chips 
```cpp
int minCostToMoveChips(int* position, int positionSize) {
    int oc = 0;
    int ec = 0;
    for(int i=0; i<positionSize; i++) {
        if(position[i] % 2 == 0)
            ec++;
        else
            oc++;
    }
    return oc < ec ? oc : ec;
}
```

### 2. Check If It Is a Straight Line (1232)
```cpp
bool checkStraightLine(int** coordinates, int coordinatesSize, int* coordinatesColSize) {
    int x1 = coordinates[0][0], y1 = coordinates[0][1];
    int x2 = coordinates[1][0], y2 = coordinates[1][1];
    for (int i = 2; i < coordinatesSize; i++) {
        int x3 = coordinates[i][0], y3 = coordinates[i][1];
        if ((x2 - x1) * (y3 - y2) != (y2 - y1) * (x3 - x2)) {
            return 0;
        }
    }
    return 1;
}
```

### 3. Average Value of Even Numbers Divisible by Three (2455)
```cpp
int averageValue(int* nums, int numsSize) {
    int sum = 0;
    int count = 0;
    for (int i = 0; i < numsSize; i++) {
        if (nums[i] % 2 == 0 && nums[i] % 3 == 0) {
            sum += nums[i];
            count++;
        }
    }
    return count > 0 ? sum / count : 0;
}
```

### 4. Difference Between Element Sum and Digit Sum of an Array (2535)
```cpp
int differenceOfSum(int* nums, int numsSize) {
    int elementSum = 0;
    int totalDigitSum = 0;
    for (int i = 0; i < numsSize; i++) {
        elementSum += nums[i];
        int num = nums[i];
        while (num > 0) {
            totalDigitSum += num % 10;
            num /= 10;
        }
    }
    return abs(elementSum - totalDigitSum);
}
```

### 5. Number of Good Pairs (1512)
```cpp
int numIdenticalPairs(int* a, int n) {
    int pc = 0;
    for(int i = 0; i < n; i++)
        for(int j = i + 1; j < n; j++)
            if(a[i] == a[j]) ++pc;
    return pc;
}
```
---

# Let's save it as a .md file.
