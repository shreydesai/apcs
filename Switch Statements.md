# Switch Statements

## Overview
* `switch` statements are used when there are multiple conditional outcomes that must be handled in a particular program
* These statements are usually preferred over multiple `else if` statements
* The `switch` statement requires some sort of variable to *switch* on - this can be anything from an `int` variable to even an `Object`
* Each `switch` statement involves a `case`, which specifies which conditional outcome to handle, and also has a `default` case, which is triggered if none of the cases are reached
* `case` statements can also be grouped together to share code
* There must be a `break` keyword after each `case` statement to indicate that the code in the statement is finished executing - if there is no `break` keyword, there will be a *fallout* where the code in every single `case` statement after that one will also be executed

## Example

## Individual `case` statements

```java
int number = 0;

switch (number) {
	case 0:
		System.out.println("The number is 0");
		break;
	case 1:
		System.out.println("The number is 1");
		break;
	case 2:
		System.out.println("The number is 2");
		break;
	default:
		System.out.println("Some other number");
}
```

## Grouped `case` statements

```java
boolean flag = true;

switch (flag) {
	case true: case false:
		System.out.println("The flag is true or false");
		break;
	default:
		System.out.println("The flag is neither true nor false");
}
```