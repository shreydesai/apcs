# Operators and Precedence

## Math Operators

### Binary Operators

* `+` - Addition
* `-` - Subtraction
* `*` - Multiplication
* `/` - Division
	* If the operands are integers, the result will be an integer. `5 / 3` will result in an answer of `1`, and not `1.6666`
	* If the operands are floating point numbers, the result will be a floating point number. `5 / 3` will result in an answer of `1.6666`, and not `1`
* `%` - Modulus (remainder)

Note: If a single operand is a floating point number, the result will also be a floating point number. `17 + 1.0` will result in an answer of `18.0`.

### Unary operators

* `-` - Negation

To clarify, the negation operator only takes one operand, instead of two, like binary operators do. `-(-17)` will result in an answer of `17`.

### Precedence

The precedence of the math operators (binary and unary) follow the order of operations. Unary operators (`-`) are evaluated first, then the multiplication (`*`), division (`/`), and modulus (`%`) operators, and finally the addition (`+`) and subtraction (`-`) operators. 

Example:
```java
9	+	16	/	3	*	7	%	8	-	5
	9	+	5	*	7	%	8	-	5
		9	+	35	%	8	-	5
			9	+	3	-	5
					7
```

## Assignment Operators

Assignment operators are used to perform a math operation on a variable, and then assign the new value of that variable to the variable.

```java
// Declare variable
int count = 0;

// Count variable equals 1
count = count + 1;
```

There are shortcuts for these types of operations:
* `+=` - Add and assign
* `-=` - Subtract and assign
* `*=` - Multiply and assign
* `/=` - Divide and assign
* `%=` - Modulo and assign

```java
// Addition
int x1 = 10;
x1 += 10;		// x1 = 20

// Subtraction
int x2 = 10;
x1 -= 10;		// x2 = 0

// Multiplication
int x3 = 10;
x3 *= 10		// x3 = 100

// Division
int x4 = 10;
x4 /= 2;		// x4 = 5

// Modulus
int x5 = 10;
x5 %= 5;		// x5 = 2
``` 

## Increment/Decrement Operators

Java provides shortcuts for incrementing and decrementing variables by `1`. Instead of performing `+=` or `-=`, you can use `++` or `--`.

```java
int count = 0;

// Increment operator
count = count + 1;
count += 1;
count++;

// Decrement operator
count = count - 1;
count -= 1;
count--;
```

Note: There is a difference between `++count` and `count++`:
* In `++count`, you increment the variable and then use it
* In `count++`, you use the variable and then increment it

```java
int a, b;

// Scenario 1
a = 0;
b = ++a;		// b = 1, a = 1

// Scenario 2
a = 0;
b = a++;		// b = 0, a = 1
```

To clarify, `++a` means **increment** and **then** use, but `a++` means **use** and then **increment**.