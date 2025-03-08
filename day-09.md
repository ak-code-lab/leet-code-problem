# LeetCode Solutions - Day 9

## 1. 171. Excel Sheet Column Number

```c
int titleToNumber(char* columnTitle) {
    int res = 0;
    for(int i=0; columnTitle[i]; i++) {
        res = res * 26 + (columnTitle[i] - 65 + 1);
    }
    return res;
}
```

## 2. 168. Excel Sheet Column Title

```c
char* convertToTitle(int columnNumber) {
    static char ans[8];
    int i = 6;
    ans[7] = '\0';
    while (columnNumber > 0) {
        columnNumber--;
        ans[i--] = (columnNumber % 26) + 'A';
        columnNumber /= 26;
    }
    return &ans[i + 1];
}
```

## 3. 405. Convert a Number to Hexadecimal

```c
char* toHex(int num) {
    static char hex[9];
    unsigned int n = num;
    int i = 0;
    if (num == 0) return "0";
    while (n > 0) {
        int remainder = n % 16;
        hex[i++] = (remainder < 10) ? (remainder + '0') : (remainder - 10 + 'a');
        n /= 16;
    }
    hex[i] = '\0';
    for (int j = 0; j < i / 2; j++) {
        char temp = hex[j];
        hex[j] = hex[i - j - 1];
        hex[i - j - 1] = temp;
    }
    return hex;
}
```

## 4. 415. Add Strings

```c
char* addStrings(char* num1, char* num2) {
    static char result[10000]; // Buffer to hold the result
    int i = strlen(num1) - 1; // Index for num1
    int j = strlen(num2) - 1; // Index for num2
    int carry = 0; // To hold carry over
    int k = 0; // Index for result
    
    // Loop until both strings are processed and there's no carry left
    while (i >= 0 || j >= 0 || carry > 0) {
        int sum = carry; // Start with carry
        
        // Add num1 digit if available
        if (i >= 0) {
            sum += num1[i] - '0'; // Convert char to int
            i--; // Move to next digit
        }
        
        // Add num2 digit if available
        if (j >= 0) {
            sum += num2[j] - '0'; // Convert char to int
            j--; // Move to next digit
        }
        
        result[k++] = (sum % 10) + '0'; // Store current digit in result
        carry = sum / 10; // Update carry
    }
    
    result[k] = '\0'; // Null-terminate the result string
    
    // Reverse the result string to get the correct order
    for (int left = 0, right = k - 1; left < right; left++, right--) {
        char temp = result[left];
        result[left] = result[right];
        result[right] = temp;
    }
    
    return result; // Return the result string
}
```

## 5. 2544. Alternating Digit Sum

```c
int alternateDigitSum(int n) {
    int reversed = 0, sum = 0, a = 1;
    
    while(n != 0) {
        int digit = n % 10;
        reversed = reversed * 10 + digit;
        n = n / 10;
    }
    
    while(reversed != 0) {
        int digit1 = reversed % 10;
        sum += a * digit1;
        a = a * -1;
        reversed = reversed / 10;
    }
    
    return sum;
}
```

## 6. 3304. Find the K-th Character in String Game I

```c
char kthCharacter(int k) {
    char initialChar = 'a';
    // Calculate the effective length of the string after sufficient operations
    long long length = 1; // The initial string length (1 for "a")
    
    // Find the length of the string after enough operations
    while (length < k) {
        length *= 2; // Each operation doubles the length of the string
    }
    
    // Now, we need to determine the K-th character
    while (k > 1) {
        // While we haven't reached the original character
        // Determine which half of the string k falls into
        long long halfLength = length / 2;
        
        // If k is in the second half
        if (k > halfLength) {
            k -= halfLength; // Move k to the position in the first half
        } else {
            // If k is in the first half, we need to go back
            length = halfLength; // Update the total length to the first half
        }
    }
    
    // Return the character by shifting from 'a'
    return (initialChar + (k - 1)) % 26 + 'a';
}
```