![cover](./cover.png)

# Day 13 - Recursion Series Part A

Today's Problems - Factorial and Fibonacci Series

## Question 1 - Factorial using recursion

Given a non-negative integer, find it's factorial using recursion

### Example

```
input: 4
output: 24

input: 5
output: 120
```

## Question 2 - Fibonacci Series

Given a number n, find the nth element in fibonacci series using recursion and after that print the series till n.

### Example

```
input = 7
output:
The 7th element in fibonacci series is: 13
The sequence is: 1, 1, 2, 3, 5, 8, 13
```

![ques](./ques.png)

## Part A - Factorial

### JavaScript Implementation

#### [Solution by @MadhavBahlMD](./JavaScript/fact_madhav.js)

```js
/**
 * @author MadhavBahlMD
 * @date 07/01/2018
 */

function factorial (num) {
    if (num <= 1)
        return 1;
    else
        return num * factorial (num-1);
}

console.log(`Factorial of 4 is: ${factorial(4)}`);
console.log(`Factorial of 5 is: ${factorial(5)}`);
```

### Java Implementation

#### [Solution](./Java/Factorial.java)

```java
/**
 * @author MadhavBahl
 * @date 07/01/2018
 */

import java.util.Scanner;

public class Factorial {
    public static int factorial (int num) {
        if (num <= 1)
            return 1;
        else
            return num * factorial(num-1);
    }

    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);
        System.out.println("/* ===== Factorial Using Recursion ===== */");
        System.out.print("\nEnter a number: ");
        int num = input.nextInt();
        System.out.println("Factorial of " + num + " is: " + factorial(num));
    }
}
```

***

***


## Part B - Fibonacci Series

### JavaScript Implementation

#### [Solution by @MadhavBahlMD](./JavaScript/fibo_madhav.js)

```js
/**
 * @author MadhavBahlMD
 * @date 07/01/2018
 */

function nthElement (n) {
    if (n <= 2) 
        return 1
    else
        return nthElement(n-1) + nthElement(n-2);
}

function fibonacci (num) {
    // Print F(n)
    console.log (`The ${num}th element in fibonacci series is: ${nthElement(num)}`);

    // Print the sequence
    let seq = '';
    for (let  i=1; i<=num; i++) 
        if (i<num)
            seq += nthElement(i) + ', ';
        else
            seq += nthElement(i);
    console.log(`The sequence is: ${seq}`);
}

fibonacci (7);
```

### Java Implementation

#### [Solution](./Java/Fibonacci.java)

```java
/**
 * @author MadhavBahl
 * @date 07/01/2018
 */

import java.util.Scanner;

public class Fibonacci {
    public static int fibonacci (int num) {
        if (num <= 2)
            return 1;
        else
            return fibonacci (num-1) + fibonacci (num-2);
    }

    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);
        System.out.println("/* ===== Fibonacci Using Recursion ===== */");
        System.out.print("\nEnter a number: ");
        int n = input.nextInt();

        // Print the nth element in the sequence
        System.out.println("\nThe " + n + "th element in fibonacci series is: " + fibonacci(n));

        // Print the sequence
        System.out.print("The sequence is: ");
        for (int i=1; i<=n; i++) {
            if (i<n)
                System.out.print(fibonacci(i) + ", ");
            else
                System.out.print(fibonacci(i));
        }
    }
}
```