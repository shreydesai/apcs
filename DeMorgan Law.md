#**Logic**
+ Logical operators are used in Boolean expressions that control the behavior of "if", "while", and "for" statements


+ `&&` (and) => both statements must be true to make the whole condition true
+ `||` (or) => both statements must be false to make the whole condition false, or at least one statement must be true to make the whole condition true
+ `!` (not) => switches true statements to false, and vice versa

## Relational Operators
+ `>`     greater than
+ `>=`    greater than or equal to
+ `<`     less than
+ `<=`    less than or equal to
+ `==`    equal to
+ `!=`   not equal to

## Example
```java
int a = 28; int b = 47; int c = 84;
if ((a<30) && (c>=85)){
    System.out.println("Hello");
}
else {
    if ((b>50) || (a>25)) {
        System.out.println("Goodbye");
    }
    else {
        System.out.println("I can't make up my mind!");
    }
    System.out.println("Here is a cool quilt with emoticons!");
}
```

# **DeMorgan's Laws (Boolean Logic)**
- `!  (  !A  &&  B  )  =>  (  A  ||  !B  )`
- `!  (  C  ||  !D  )  =>  (  !C  &&  D  )`
- `!  ( x  >  5  )  =>  (  x  <=  5  )`
+ basically opposites
+ can go backwaards and forwards

## Example Question
+ The expression `!((m < n) || (m != 5))` is equivalent to which of the following?
+ a. `(m < n) && (m != 5)`
+ b. `! (m < n) || ! (m != 5)`
+ c. `(m > n) && (m == 5)`
+ d. `(m >= n) && (m == 5)`
+ e. `(m <= n) || ! (m == 5)`
