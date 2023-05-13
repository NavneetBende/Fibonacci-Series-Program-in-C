# Fibonacci-Series-Program-in-C

Write a C Program to find Fibonacci series up to n
The sequence is a Fibonacci series in C where the next number is the sum of the previous two numbers. The first two terms of the Fibonacci sequence is started from 0, 1.
Fibonacci series upto n terms in c
What is Fibonacci Series
It’s a unique sequence where the next number is the sum of previous two numbers.

Where the first two terms are always 0 and 1
In mathematical terms :
Fn = Fn-1 + Fn-2

Where,
F0 : 0
F1 : 1
Example Series
The series Looks like : 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144 …
Fibonacci Series in C
While loop in C
Method 1
Run
#include<stdio.h>

int main()
{
    int n = 10;
    int a = 0, b = 1;
    
    // printing the 0th and 1st term
    printf("%d, %d",a,b);
    
    int nextTerm;
    
    // printing the rest of the terms here
    for(int i = 2; i < n; i++){
        nextTerm = a + b;
        a = b;
        b = nextTerm;
        
        printf("%d, ",nextTerm);
    }

    return 0;
}
Output
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 
While loop in C
Method 2 (Recursion/static variable)
This method uses recursion in C, also uses static variables in C

Run
#include<stdio.h>

int printFib(int n){
    
    static int a = 0, b = 1, nextTerm;    
    if(n > 0)
    {    
        nextTerm = a + b;    
        a = b;    
        b = nextTerm;    
    
        printf("%d, ",nextTerm);
        printFib(n-1);    
    }
    
}

int main()
{
    int n = 10;
    
    printf("0, 1, ");
    
    // n-2 as 2 terms already printed
    printFib(n-2);

    return 0;
}
Output
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 
Related Pages
Armstrong number

Armstrong number in a given range

Fibonacci Series upto nth term 

Find the Nth Term of the Fibonacci Series

Factorial of a number

Power of a number

Method 3 (Recursion)
This method uses recursion in C, rather than static variables, we use pure recursion here.


Run

#include<stdio.h>

int getFib(int n){
    
    if(n <= 1)
        return n;
        
    return getFib(n-1) + getFib(n-2);
    
}

int main()
{
    int n = 10;

    for(int i = 0; i < n; i++)
        printf("%d, ",getFib(i));

    return 0;
}
Output
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 
Method 4 (Direct Formula)
We can use direct formula to find nth term of Fibonacci Series as –

Fn = {[(√5 + 1)/2] ^ n} / √5

Run

#include<stdio.h> 
#include<math.h> 

int getFibo(double phi, int n) {
    
    for(int i = 0; i <= n; i++)
    {
        // setting .0 precision so all leading decimals are not printed
        // else would have printed 1.000000, 1.000000, 2.000000 so on....
        printf("%.0lf, ",round(pow(phi, i) / sqrt(5)));
    }
}

int main ()
{
    int n = 15;
    double phi = (1 + sqrt(5)) / 2;
    getFibo(phi, n);
    
    return 0;
}
Output
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 
