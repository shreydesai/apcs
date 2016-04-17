# **While Loops**
+ `while` loops have a condition that must be satisfied in order to implement the code inside the `while` loop
+ The quantity of iterations is unknown for the while loop
+ This is a pretest loop

## Example
```java
double num = 24.0;
while (num <= 32) {
    System.out.println(num + " ");
    num += 1.25;
}
```

# **Do While Loops**
+ Similar to a `while` loop except that the code will run the `do-while` loop at least once
    - After the code has gone through the loop the first time, the condition must be satisfied to go through the `do-while` loop again
+ This is a post-test loop

## Example
```java
int m = 1;
do {
    System.out.println(m + "  " + (m-1));
    m+=2;
}
while (m != 10);
```
