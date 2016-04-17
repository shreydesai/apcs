# Recursion

## Overview
* Recursion is the process of calling a function over and over again until it reaches a base case, finally terminating the process and yielding a result
* The base case is usually evaluated through a conditional statement
    * If the `boolean` statement is `true`, then the recursive process terminates
    * If the `boolean` statement is `false`, then the function calls itself and keeps going until it reaches a base case
* What recursion does is work its way to the base case, calling the function over and over again; when the base case is reached, usually some value is returned, and this value makes its way up to the front of the stack, and this is the value that is returned to the user
* It is wise to be extremely careful with recursion - if you do not reach a base case, your program and/or computer can crash due to memory overload because of thousands of recursive calls

## Example

### Number of calls

```java
public static int calls(int depth) {
    if (depth == 10) {
        return 1;
    } else {
        return calls(depth + 1);
    }
}

public static void main(String[] args) {

    // Finds the number of recursive calls
    // with 10 as the upper limit
    calls(0);
}
```

### Fibonacci sequence

```java
public static int fib(int n) {
    if (n == 0) {
        return 0;
    } else if (n == 1) {
        return 1;
    } else {
        return fib(n - 1) + fib(n - 2);
    }
}

public static void main(String[] args) {

    // Finds the 10th number in the Fibonacci sequence
    fib(10);
}
```
