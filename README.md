// Program to Check Vowel or consonant
#include <stdio.h>
int main()
{
    char c;
    int lowercase_vowel, uppercase_vowel;
    printf("Enter an alphabet: ");
    scanf("%c", &c);

    // evaluates to 1 if variable c is a lowercase vowel
    lowercase_vowel = (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u');

    // evaluates to 1 if variable c is a uppercase vowel
    uppercase_vowel = (c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U');

    // evaluates to 1 (true) if c is a vowel
    if (lowercase_vowel || uppercase_vowel)
        printf("%c is a vowel.", c);
    else
        printf("%c is a consonant.", c);
    return 0;
}

// Program to Check Leap Year
#include <stdio.h>
int main()
{
    int year;
    printf("Enter a year: ");
    scanf("%d", &year);

    // leap year if perfectly divisible by 400
    if (year % 400 == 0)
    {
        printf("%d is a leap year.", year);
    }
    // not a leap year if divisible by 100
    // but not divisible by 400
    else if (year % 100 == 0)
    {
        printf("%d is not a leap year.", year);
    }
    // leap year if not divisible by 100
    // but divisible by 4
    else if (year % 4 == 0)
    {
        printf("%d is a leap year.", year);
    }
    // all other years are not leap years
    else
    {
        printf("%d is not a leap year.", year);
    }

    return 0;
}

// Check Positive or Negative
#include <stdio.h>

int main()
{

    double num;
    printf("Enter a number: ");
    scanf("%lf", &num);
    if (num <= 0.0)
    {
        if (num == 0.0)
            printf("You entered 0.");
        else
            printf("You entered a negative number.");
    }
    else
        printf("You entered a positive number.");

    return 0;
}

// Multiplication Table Up to 10
#include <stdio.h>
int main()
{
    int n;
    printf("Enter an integer: ");
    scanf("%d", &n);

    for (int i = 1; i <= 10; ++i)
    {
        printf("%d * %d = %d \n", n, i, n * i);
    }
    return 0;
}

// Program to Check Alphabet
#include <stdio.h>
int main()
{
    char c;
    printf("Enter a character: ");
    scanf("%c", &c);

    if ((c >= 'a' && c <= 'z') || (c >= 'A' && c <= 'Z'))
        printf("%c is an alphabet.", c);
    else
        printf("%c is not an alphabet.", c);

    return 0;
}

// Program to Print English Alphabets
#include <stdio.h>
int main()
{
    char c;
    for (c = 'A'; c <= 'Z'; ++c)
        printf("%c ", c);
    return 0;
}

// Power of a Number Using the while Loop
#include <stdio.h>
int main()
{
    int base, exp;
    long double result = 1.0;
    printf("Enter a base number: ");
    scanf("%d", &base);
    printf("Enter an exponent: ");
    scanf("%d", &exp);

    while (exp != 0)
    {
        result *= base;
        --exp;
    }
    printf("Answer = %.0Lf", result);
    return 0;
}

// Program to Check Palindrome
#include <stdio.h>
int main()
{
    int n, reversed = 0, remainder, original;
    printf("Enter an integer: ");
    scanf("%d", &n);
    original = n;

    // reversed integer is stored in reversed variable
    while (n != 0)
    {
        remainder = n % 10;
        reversed = reversed * 10 + remainder;
        n /= 10;
    }

    // palindrome if orignal and reversed are equal
    if (original == reversed)
        printf("%d is a palindrome.", original);
    else
        printf("%d is not a palindrome.", original);

    return 0;
}

// Program to Check Prime Number
#include <stdio.h>

int main()
{

    int n, i, flag = 0;
    printf("Enter a positive integer: ");
    scanf("%d", &n);

    // 0 and 1 are not prime numbers
    // change flag to 1 for non-prime number
    if (n == 0 || n == 1)
        flag = 1;

    for (i = 2; i <= n / 2; ++i)
    {

        // if n is divisible by i, then n is not prime
        // change flag to 1 for non-prime number
        if (n % i == 0)
        {
            flag = 1;
            break;
        }
    }

    // flag is 0 for prime numbers
    if (flag == 0)
        printf("%d is a prime number.", n);
    else
        printf("%d is not a prime number.", n);

    return 0;
}

// Check Armstrong Number of three digits
#include <stdio.h>
int main()
{
    int num, originalNum, remainder, result = 0;
    printf("Enter a three-digit integer: ");
    scanf("%d", &num);
    originalNum = num;

    while (originalNum != 0)
    {
        // remainder contains the last digit
        remainder = originalNum % 10;

        result += remainder * remainder * remainder;

        // removing last digit from the orignal number
        originalNum /= 10;
    }

    if (result == num)
        printf("%d is an Armstrong number.", num);
    else
        printf("%d is not an Armstrong number.", num);

    return 0;
}

// Factors of a Positive Integer
#include <stdio.h>
int main()
{
    int num, i;
    printf("Enter a positive integer: ");
    scanf("%d", &num);
    printf("Factors of %d are: ", num);
    for (i = 1; i <= num; ++i)
    {
        if (num % i == 0)
        {
            printf("%d ", i);
        }
    }
    return 0;
}

// Simple Calculator using switch Statement
#include <stdio.h>

int main()
{

    char op;
    double first, second;
    printf("Enter an operator (+, -, *, /): ");
    scanf("%c", &op);
    printf("Enter two operands: ");
    scanf("%lf %lf", &first, &second);

    switch (op)
    {
    case '+':
        printf("%.1lf + %.1lf = %.1lf", first, second, first + second);
        break;
    case '-':
        printf("%.1lf - %.1lf = %.1lf", first, second, first - second);
        break;
    case '*':
        printf("%.1lf * %.1lf = %.1lf", first, second, first * second);
        break;
    case '/':
        printf("%.1lf / %.1lf = %.1lf", first, second, first / second);
        break;
    // operator doesn't match any case constant
    default:
        printf("Error! operator is not correct");
    }

    return 0;
}

// Example 1: C Program to Convert Binary Number to Decimal
//  convert binary to decimal

#include <stdio.h>
#include <math.h>

// function prototype
int convert(long long);

int main()
{

    long long n;

    printf("Enter a binary number: ");
    scanf("%lld", &n);

    printf("%lld in binary = %d in decimal", n, convert(n));

    return 0;
}

// function definition
int convert(long long n)
{

    int dec = 0, i = 0, rem;

    while (n != 0)
    {

        // get remainder of n divided by 10
        rem = n % 10;

        // divide n by 10
        n /= 10;

        // multiply rem by (2 ^ i)
        // add the product to dec
        dec += rem * pow(2, i);

        // increment i
        ++i;
    }

    return dec;
}

// GCD Using for loop and if Statement
#include <stdio.h>
int main()
{
    int n1, n2, i, gcd;

    printf("Enter two integers: ");
    scanf("%d %d", &n1, &n2);

    for (i = 1; i <= n1 && i <= n2; ++i)
    {
        // Checks if i is factor of both integers
        if (n1 % i == 0 && n2 % i == 0)
            gcd = i;
    }

    printf("G.C.D of %d and %d is %d", n1, n2, gcd);

    return 0;
}

// Reverse an Integer
#include <stdio.h>

int main()
{

    int n, reverse = 0, remainder;

    printf("Enter an integer: ");
    scanf("%d", &n);

    while (n != 0)
    {
        remainder = n % 10;
        reverse = reverse * 10 + remainder;
        n /= 10;
    }

    printf("Reversed number = %d", reverse);

    return 0;
}
/* Question: transpose of a matrix*/
#include <stdio.h>

void transpose(int mat[10][10], int m, int n) {
    int trans[10][10];
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            trans[j][i] = mat[i][j];
        }
    }
    printf("Transpose of the matrix is:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            printf("%d ", trans[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int mat[10][10], m, n;
    printf("Enter the number of rows and columns of the matrix\n");
    scanf("%d%d", &m, &n);
    printf("Enter the elements of the matrix\n");
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &mat[i][j]);
        }
    }
    transpose(mat, m, n);
    return 0;
}


/* Question: determinant of a matrix*/
#include <stdio.h>
#include <math.h>

double determinant(int mat[10][10], int n) {
    double det = 0;
    if (n == 2) {
        return (mat[0][0] * mat[1][1] - mat[0][1] * mat[1][0]);
    }
    int sign = 1;
    for (int i = 0; i < n; i++) {
        double sub_det = determinant(mat, n - 1);
        det += sign * mat[0][i] * sub_det;
        sign *= -1;
    }
    return det;
}

int main() {
    int mat[10][10], n;
    printf("Enter the number of rows and columns of the matrix\n");
    scanf("%d", &n);
    printf("Enter the elements of the matrix\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &mat[i][j]);
        }
    }
    double det = determinant(mat, n);
    printf("Determinant of the matrix is %.2f\n", det);
    return 0;
}


/* Question: Area of circle*/
#include <stdio.h>
#define PI 3.14159

double area(double radius) {
    return PI * radius * radius;
}

int main() {
    double r;
    printf("Enter the radius of the circle: ");
    scanf("%lf", &r);
    printf("Area of the circle = %.2f\n", area(r));
    return 0;
}



/* Question: GCD of two given numbers*/
#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0)
        return a;
    else
        return gcd(b, a % b);
}

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d%d", &a, &b);
    printf("GCD of %d and %d = %d\n", a, b, gcd(a, b));
    return 0;
}

/* Question: Program to find the sum of digits of a number:*/
#include <stdio.h>
int sum_of_digits(int n) {
    if (n == 0)
        return 0;
    else
        return (n % 10 + sum_of_digits(n / 10));
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("Sum of digits of %d = %d\n", num, sum_of_digits(num));
    return 0;
}

/* Question: Program to find the reverse of a number::*/
#include <stdio.h>
int reverse(int n) {
    if (n == 0)
        return 0;
    else
        return (n % 10 * (int)pow(10, (int)log10(n)) + reverse(n / 10));
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("Reverse of %d = %d\n", num, reverse(num));
    return 0;
}

/* Question: Program to find the factorial of a number using recursion::*/
#include <stdio.h>

int factorial(int n) {
    if (n == 0)
        return 1;
    else
        return n * factorial(n - 1);
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("Factorial of %d = %d\n", num, factorial(num));
    return 0;
}


/* Question: Program to find the area of a rectangle::*/
#include <stdio.h>

double area(double length, double width) {
    return length * width;
}

int main() {
    double l, w;
    printf("Enter the length and width of the rectangle: ");
    scanf("%lf%lf", &l, &w);
    printf("Area of the rectangle = %.2f\n", area(l, w));
    return 0;
}



/* Question:Program to find the reverse of a string:*/
#include <stdio.h>
#include <string.h>

void reverse(char *str) {
    int len = strlen(str);
    for (int i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - i - 1];
        str[len - i - 1] = temp;
    }
}

int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);
    reverse(str);
    printf("Reversed string: %s\n", str);
    return 0;
}



/* Question:Program to find the factorial of a number using dynamic memory allocation::*/
#include <stdio.h>
#include <stdlib.h>

int factorial(int n) {
    if (n == 0)
        return 1;
    else
        return n * factorial(n - 1);
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    int *fact = (int *)malloc((num + 1) * sizeof(int));
    fact[0] = 1;
    for (int i = 1; i <= num; i++) {
        fact[i] = i * fact[i - 1];
    }
    printf("Factorial of %d = %d\n", num, fact[num]);
    free(fact);
    return 0;
}



/* Question:Program to find the maximum and minimum elements in an array::*/
#include <stdio.h>

void find_max_min(int arr[], int n, int *max, int *min) {
    *max = arr[0];
    *min = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > *max) {
            *max = arr[i];
        }
        if (arr[i] < *min) {
            *min = arr[i];
        }
    }
}

int main() {
    int arr[10], n, max, min;
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);
    printf("Enter the elements of the array: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    find_max_min(arr, n, &max, &min);
    printf("Maximum element in the array = %d\n", max);
    printf("Minimum element in the array = %d\n", min);
    return 0;
}



/* Question:Program to find the number of occurrences of an element in an array:::*/
#include <stdio.h>

int count(int arr[], int n, int x) {
    int count = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] == x) {
            count++;
        }
    }
    return count;
}

int main() {
    int arr[10], n, x;
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);
    printf("Enter the elements of the array: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    printf("Enter the element to find its occurrences: ");
    scanf("%d", &x);
    printf("%d occurs %d times in the array\n", x, count(arr, n, x));
    return 0;
}



/* Question:Program to find the second largest element in an array:*/
#include <stdio.h>

int second_largest(int arr[], int n) {
    int max1 = arr[0], max2 = arr[1];
    if (max2 > max1) {
        int temp = max1;
        max1 = max2;
        max2 = temp;
    }
    for (int i = 2; i < n; i++) {
        if (arr[i] > max1) {
            max2 = max1;
            max1 = arr[i];
        } else if (arr[i] > max2 && arr[i] != max1) {
            max2 = arr[i];
        }
    }
    if (max2 == -1) {
        printf("There is no second largest element\n");
    } else {
        printf("Second largest element in the array = %d\n", max2);
    }
    return 0;
}

int main() {
    int arr[10], n;
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);
    printf("Enter the elements of the array: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    second_largest(arr, n);
    return 0;
}


/* Question:Program to find the maximum element in an array:*/
#include <stdio.h>

int max(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    return max;
}

int main() 
{
    int arr[10], n;
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);
    printf("Enter the elements of the array: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    printf("Maximum element in the array = %d\n", max(arr, n));
    return 0;
}
