# Variable Casting

## Overview

* Variable casting is used when the data type of a variable is temporarily converted to another primitive data type. The general formula for variable casting is: `<variable type A> <variable name> = (<variable type A>) <data>`.
* Common variable casting conversions include:
	* `int` to `double` and `double` to `int`
	* `int` to `char` and `char` to `int`
* Some primitive data types cannot be casted to another, such as `boolean` to `int`, or `short` to `long` - doing so will throw an exception

## Examples

**`int` and `double`**

```java
int x1 = 5;

// Casting an integer to a double
double x2 = (double) x1;

System.out.println(x2);		// Prints 5.0
```

**`int` and `char`**

```java
char x1 = 'a';

// Casting a char to an integer
int x2 = (int) x1;

System.out.println(x2);		// Prints 97
```

## Miscellaneous

More on `int` to `char` casting:
* `char` data types are actually stored as integers in memory
* These data types follow the American Standard Code for Information Interchange, or ASCII, coding
* Refer to [this table](http://www.asciitable.com/) for a comprehensive list on what the corresponding integer is for a character