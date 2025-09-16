# HCF of Two Numbers - C Program

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
