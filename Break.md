# Break

## Overview

* As the name suggests, the `break` keyword is used to *break* out of a conditional statement or also a loop
* Generally, `break` keywords are used when the body of a conditional statement or loop is no longer needed, such as when something is found or a task is completed

## Example

## `break` in an `if` statement

```java
if (2 + 2 == 4) {
	break;
	System.out.println(“Hello”);
	System.out.println(“Hello world”);
}

```

Note: The two `System.out.println` statements are not evaluated because the `break` keyword exits the entirety of the `if` statement.

## `break` in a `for` loop
```java
int target = 2;
int[] numbers = {3, 7, 2, 5, 10, 12, 4, 6};

for (int i = 0; i < numbers.length; i++) {
	if (numbers[i] == target) {
		System.out.println(“Found the number at index “ + i);
		break;
	}
}
```

Note: The `for` loop exits at index `3` because the target of `2` is found, and the `break` keyword forces Java to terminate the loop. 