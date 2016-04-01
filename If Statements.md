# If Statements

## Overview

* `If` and `else` statements are the most basic type of control structure
* If you require more than two choices, there is an additional `else if` statement
* You can navigate these conditional statements through a `boolean` expression
	* If the `boolean` condition is `true`, then the code in the `if` statement is evaluated
	* If the `boolean` condition is `true`, then the code in the `else` statement is evaluated
	* If the `boolean` condition in the `if` statement is `false`, but the `boolean` condition in the `else if` statement is `true`, then the code in the `else if` statement is evaluated

The basic structure of an `if`/`else` statement is as follows:

```java
if (<boolean condition>) {
	// Code that goes in the if statement
} else {
	// Code that goes in the else statement
}
```

As stated above, you can also add `else if` statements if you would like to have more than two options.

```java
if (<boolean condition>) {
	// Code that goes in the if statement
} else if (<boolean condition>) {
	// Code that goes in the else if statement
} else {
	// Code that goes in the else statement
}
```

## Miscellaneous

* You can have more than one `else if` statements, but you can only have one `if` and one `else` statement in a single conditional expression
* The `else` statement is optional in a conditional expression
* The `else` statement does not require a boolean expression
* You can also have further `if` and `else` statements within an `if` or `else` statement for greater conditional control 

## Examples

### One `if`/`else if`/`else` statement
```java
int count = 10;

if (count < 10) {
	System.out.println("Number is below 10");
} else if (count == 10) {
	System.out.println("Number is equal to 10");
} else {
	System.out.println("Number is greater than 10");
}
```

### Nested `if`/`else` statements

```java
int count = 10;
if (count < 10) {
	if (count % 2 == 0) {
		System.out.println("Number is less than 10 AND even");
	} else {
		System.out.println("Number is less than 10 AND odd");
	}
} else if (count == 10) {
	System.out.println("Number is equal to 10");
} else {
	System.out.println("Number is greater than 10");
}
```