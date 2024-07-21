# Assignment-11

1. Function to calculate LCM of two numbers (TSRS)
   #include <stdio.h>

int gcd(int a, int b) {
    if (b == 0)
        return a;
    return gcd(b, a % b);
}

int lcm(int a, int b) {
    return (a * b) / gcd(a, b);
}

int main() {
    int a = 15, b = 20;
    printf("LCM of %d and %d is %d\n", a, b, lcm(a, b));
    return 0;
}

2. Function to calculate HCF of two numbers (TSRS)
   #include <stdio.h>

int hcf(int a, int b) {
    if (b == 0)
        return a;
    return hcf(b, a % b);
}

int main() {
    int a = 15, b = 20;
    printf("HCF of %d and %d is %d\n", a, b, hcf(a, b));
    return 0;
}

3. #include <stdio.h>
#include <stdbool.h>

bool isPrime(int n) {
    if (n <= 1)
        return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0)
            return false;
    }
    return true;
}

int main() {
    int n = 29;
    if (isPrime(n))
        printf("%d is a prime number\n", n);
    else
        printf("%d is not a prime number\n", n);
    return 0;
}

4. #include <stdio.h>
#include <stdbool.h>

bool isPrime(int n) {
    if (n <= 1)
        return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0)
            return false;
    }
    return true;
}

int nextPrime(int n) {
    int next = n + 1;
    while (!isPrime(next)) {
        next++;
    }
    return next;
}

int main() {
    int n = 29;
    printf("Next prime number after %d is %d\n", n, nextPrime(n));
    return 0;
}

5. #include <stdio.h>
#include <stdbool.h>

bool isPrime(int n) {
    if (n <= 1)
        return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0)
            return false;
    }
    return true;
}

void printNPrimes(int n) {
    int count = 0, num = 2;
    while (count < n) {
        if (isPrime(num)) {
            printf("%d ", num);
            count++;
        }
        num++;
    }
    printf("\n");
}

int main() {
    int n = 10;
    printf("First %d prime numbers are: ", n);
    printNPrimes(n);
    return 0;
}

6. #include <stdio.h>
#include <stdbool.h>

bool isPrime(int n) {
    if (n <= 1)
        return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0)
            return false;
    }
    return true;
}

void printPrimesBetween(int start, int end) {
    for (int i = start; i <= end; i++) {
        if (isPrime(i)) {
            printf("%d ", i);
        }
    }
    printf("\n");
}

int main() {
    int start = 10, end = 50;
    printf("Prime numbers between %d and %d are: ", start, end);
    printPrimesBetween(start, end);
    return 0;
}

7. #include <stdio.h>

void printFibonacci(int n) {
    int a = 0, b = 1, c;
    if (n >= 1)
        printf("%d ", a);
    if (n >= 2)
        printf("%d ", b);
    for (int i = 3; i <= n; i++) {
        c = a + b;
        printf("%d ", c);
        a = b;
        b = c;
    }
    printf("\n");
}

int main() {
    int n = 10;
    printf("First %d terms of Fibonacci series are: ", n);
    printFibonacci(n);
    return 0;
}

8. #include <stdio.h>

void printPascalTriangle(int n) {
    int arr[n][n];
    for (int line = 0; line < n; line++) {
        for (int i = 0; i <= line; i++) {
            if (i == 0 || i == line)
                arr[line][i] = 1;
            else
                arr[line][i] = arr[line-1][i-1] + arr[line-1][i];
            printf("%d ", arr[line][i]);
        }
        printf("\n");
    }
}

int main() {
    int n = 5;
    printf("Pascal's Triangle with %d levels:\n", n);
    printPascalTriangle(n);
    return 0;
}

9. #include <stdio.h>

int square(int n) {
    return n * n;
}

int main() {
    int num = 5;
    printf("Square of %d is %d\n", num, square(num));
    return 0;
}

10. #include <stdio.h>

int factorial(int n) {
    if (n == 0 || n == 1)
        return 1;
    int fact = 1;
    for (int i = 2; i <= n; i++)
        fact *= i;
    return fact;
}

double sumSeries() {
    double sum = 0.0;
    for (int i = 1; i <= 5; i++) {
        sum += (double)factorial(i) / i;
    }
    return sum;
}

int main() {
    printf("Sum of the series 1!/1 + 2!/2 + 3!/3 + 4!/4 + 5!/5 is %.2lf\n", sumSeries());
    return 0;
}
