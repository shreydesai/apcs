# Boolean operators

## Overview

* `boolean` operators are very important, as they are used in various control structures and iteration loops
* In order to make `boolean` operators more specific, symbols such as **and** (`&&`), **or** (`||`), and **not** (`!`) are used

## `and` keyword

* `and` is used when two elements must evaluate to `true` in order for the overall `boolean` expression to be `true`
* The general formula is: `<boolean expression> && <boolean expression>`

```java
if (2 + 2 == 4 && 1 + 1 == 2) {
	System.out.println(“Both boolean operations are true”);
}
```

## `or` keyword

* `or` is used when only one of the two elements must evaluate to `true` in order for the overall `boolean` expression to be `true`
* The general formula is: `<boolean expression> || <boolean expression>`

```java
int count = 10;

if (count == 10 || false) {
	System.out.println(“One of the boolean expressions is true”);
}
```

## `not` keyword

* `not` is used to negate an expression, or to turn it into its opposite
* For example, `!true` would evaluate to `false`, and `!false` would evaluate to `true`

```java
if (!(10 + 10 == 0) && !(false)) {
	System.out.println(“The boolean expression above evaluates to true”);
}
```