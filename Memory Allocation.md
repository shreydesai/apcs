# Memory Allocation

## Overview
* Java allocates memory for primitive data types and objects differently
	* Primitive data type variables have their value directly stored into them
	* Object variables merely hold a **reference** to where the actual object is stored - this is also known as a *hexadecimal address* or *hex address* for short
* For objects, `null` indicates **nothing** or the absence of a reference to an object

## Examples

### Primitive data types

1) The contents of `v1` are directly passed on to `v2`.

```java
int v1 = 10;
int v2 = v1;

### Objects

1) The reference, or hex address, of `s1` is passed onto `s2`, so both variables **point** to the same location.

```java
String s1 = “Computer Science”;
String s2 = s1;
```

2) Using `System.out.println` on the variable `s3` would throw a `NullPointerException` because the variable does not point to anything, and does not have a location in memory. It is considered garbage and therefore discarded.

```java
String s3 = null;
System.out.println(s3);

// Equivalent to

String s4;
System.out.println(s4);
```
