# LeetCode Solutions - Day 10

## 1. 3024. Type of Triangle

```c
char* triangleType(int* nums, int numsSize) {
    if(nums[0]+nums[1]>nums[2] && nums[0]+nums[2]>nums[1] && nums[1]+nums[2]>nums[0]) {
        //a=b=c
        if(nums[0]==nums[1] && nums[1]==nums[2])
            return "equilateral";
        //a=b or b=c or c=a
        if(nums[0]==nums[1] || nums[1]==nums[2] || nums[0]==nums[2])
            return "isosceles";
        //a!=b!=c
        if(nums[0]!=nums[1] && nums[1]!=nums[2] && nums[2]!=nums[0])
            return "scalene";
    }
    //a+b > c
    return "none";
}
```

## 2. 389. Find the Difference

```c
char findTheDifference(char* s, char* t) {
    int charCount[128] = {0};
    for(int i=0; s[i]!='\0'; i++)
        charCount[(int)s[i]]++;
    for(int i=0; t[i]!='\0'; i++)
        charCount[(int)t[i]]--;
    for(int i=0; i<128; i++)
        if(charCount[i] == -1)
            return (char)i;
    return '\0';
}
```

## 3. 2864. Maximum Odd Binary Number

```c
char* maximumOddBinaryNumber(char* s) {
    int onesCount = 0, zerosCount = 0;
    for (int i = 0; s[i] != '\0'; i++) {
        if (s[i] == '1') {
            onesCount++; //5
        } else {
            zerosCount++; //2
        }
    }
    for (int i = 0; i < onesCount-1 ; i++) {
        s[i] = '1';
    }
    for (int i = onesCount - 1; i < onesCount + zerosCount - 1; i++) {
        s[i] = '0';
    }
    s[onesCount + zerosCount - 1] = '1';
    s[onesCount + zerosCount] = '\0';
    return s;
}
```

## 4. 1684. Count the Number of Consistent Strings

```c
int countConsistentStrings(char * allowed, char ** words, int wordsSize){
    int allowedFreq[26] = {0}; //aab a - 2 b - 1
    for(int i=0; allowed[i]; i++)
        allowedFreq[allowed[i]-'a'] = 1;
    
    int consistentWord = 0;
    for(int i=0; i<wordsSize; i++){
        int flag = 1;
        for(int j=0; words[i][j]; j++){
            if(allowedFreq[words[i][j]-'a'] == 0){
                flag = 0;
                break;
            }
        }
        
        if(flag)
            consistentWord++;
    }
    
    return consistentWord;
}
```

## 5. 2525. Categorize Box According to Criteria

```c
char* categorizeBox(int length, int width, int height, int mass) {
    int isBulky = (length >= 10000 || width >= 10000 || height >= 10000 || volume >= 1000000000);
    int isHeavy = (mass >= 100);
    
    if (isBulky && isHeavy) {
        return "Both";
    } else if (isBulky) {
        return "Bulky";
    } else if (isHeavy) {
        return "Heavy";
    } else {
        return "Neither";
    }
}
```

## 6. 2351. First Letter to Appear Twice

```c
char repeatedCharacter(char* s) {
    int seen[26] = {0};
    for (int i = 0; s[i] != '\0'; i++) {
        int index = s[i] - 'a';
        if (seen[index]) {
            return s[i];
        }
        seen[index] = 1;
    }
    return '\0';
}
```

## 7. 1812. Determine Color of a Chessboard Square

```c
bool squareIsWhite(char* c) {
    int row = c[0]-97+1;
    int col = c[1]-48+1;
    return (row+col)%2==0;
}
```

## 8. 3274. Check if Two Chessboard Squares Have the Same Color

```c
bool checkTwoChessboards(char* c1, char* c2) {
    int col1 = c1[0]-97+1;
    int row1 = c1[1]-48+1;
    int col2 = c2[0]-97+1;
    int row2 = c2[1]-48+1;
    return (row1 + col1) % 2 == (row2 + col2) % 2;
}
```

## 9. 1903. Largest Odd Number in String

```c
char* largestOddNumber(char* num) {
    int len = strlen(num);
    for (int i = len - 1; i >= 0; i--) {
        if (num[i] % 2 != 0) {
            num[i + 1] = '\0';
            return num;
        }
    }
    return "";
}
```

## 10. 3222. Find the Winning Player in Coin Game

```c
char* losingPlayer(int x, int y) {
    int turns = 0;
    while(x>=1 && y>=4) {
        turns +=1;
        x -= 1;
        y -= 4;
    }
    if(turns%2==0)
        return "Bob";
    return "Alice";
}
```