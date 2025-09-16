# HCF of Two Numbers - C Program

## Method 1: Using Euclidean Algorithm

```c
#include <stdio.h>

int main() {
    int num1, num2, hcf;

    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    // Find HCF using Euclidean algorithm
    while (num2 != 0) {
        int temp = num2;
        num2 = num1 % num2;
        num1 = temp;
    }
    hcf = num1;

    printf("HCF of the two numbers is: %d\n", hcf);

    return 0;
}
```

## Method 2: Using Subtraction

```c
#include<stdio.h>

int main()
{
    int num1 = 144, num2 = 32, hcf = 1;

    while (num1 != num2)
    {
        if (num1 > num2)
            num1 -= num2;
        else
            num2 -= num1;
    }

    printf("The HCF : %d", num1);

    return 0;
}
```

# LCM of Two Numbers - C Program

## Method 1: Using HCF Formula

```c
#include <stdio.h>

int main() {
    int num1, num2, lcm, hcf, temp1, temp2;

    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    temp1 = num1;
    temp2 = num2;

    // Find HCF using Euclidean algorithm
    while (temp2 != 0) {
        int temp = temp2;
        temp2 = temp1 % temp2;
        temp1 = temp;
    }
    hcf = temp1;

    // Calculate LCM using formula: LCM = (num1 * num2) / HCF
    lcm = (num1 * num2) / hcf;

    printf("LCM of %d and %d is: %d\n", num1, num2, lcm);

    return 0;
}
```

## Method 2: Simple Loop Method

```c
#include <stdio.h>

int main() {
    int num1, num2, max;

    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    max = (num1 > num2) ? num1 : num2;

    while (1) {
        if (max % num1 == 0 && max % num2 == 0) {
            printf("LCM of %d and %d is: %d\n", num1, num2, max);
            break;
        }
        ++max;
    }

    return 0;
}
```

## Method 3: Using For Loop

```c
#include<stdio.h>

int main()
{
    int num1 = 36, num2 = 60, lcm;

        // finding the larger number here
        int max = (num1 > num2)? num1 : num2;
        
        // LCM will atleast be >= max(num1, num2)
        // Largest possibility of LCM will be num1*num2
        for(int i = max ; i <= num1*num2 ; i++)
        {
            if(i % num1 == 0 && i % num2 == 0){
                lcm = i;
                break;
            }
        }
    
    printf("The LCM: %d", lcm);
    
    return 0;
}
```

# GCD of Two Numbers - C Program

## Method 1: Using Euclidean Algorithm (Iterative)

```c
#include <stdio.h>

int main() {
    int num1, num2, gcd;

    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    // Find GCD using Euclidean algorithm
    while (num2 != 0) {
        int temp = num2;
        num2 = num1 % num2;
        num1 = temp;
    }
    gcd = num1;

    printf("GCD of the two numbers is: %d\n", gcd);

    return 0;
}
```

## Method 2: Using Recursion

```c
#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0)
        return a;
    return gcd(b, a % b);
}

int main() {
    int num1, num2;

    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    printf("GCD of %d and %d is: %d\n", num1, num2, gcd(num1, num2));

    return 0;
}
```

# Binary to Decimal Conversion - C Program

```c
#include <stdio.h>
#include <string.h>
#include <math.h>

int main() {
    char binary[65];
    int decimal = 0, length, i;

    printf("Enter a binary number: ");
    scanf("%s", binary);

    length = strlen(binary);

    for (i = 0; i < length; i++) {
        if (binary[i] == '1') {
            decimal += pow(2, length - 1 - i);
        }
    }

    printf("Decimal equivalent: %d\n", decimal);

    return 0;
}
