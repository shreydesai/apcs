# **While Loops**
+ while loops have a condition that must be satisfied in order to implement the code inside the while loop
+ the quantity of iterations is unknown for the while loop
+ this is a pretest loop

## Example
```javascript
double num = 24.0;
while (num <= 32) {
    System.out.println(num + " ");
    num += 1.25;
}
```

# **Do While Loops**
+ similar to a while loop except that the code will run the do-while loop at least once
+ this is a post-test loop

## Example
```javascript
int m = 1;
do{
    System.out.println(m + "  " + (m-1));
    m+=2;
}
while (m != 10);
```
