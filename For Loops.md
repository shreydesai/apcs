# For Loops

## Overview
* `for` loops are used to iterate through a sequence of primitive data types or objects
* It is a pre-check loop, which means that if its `boolean` condition evaluates to `false`, then the body of the loop will not be executed
* The `for` loop has three parts: the variable, `boolean` condition, and increment/decrement status
* There is also a variant of the `for` loop, called the `for each` loop
	* This is generally used to loop through arrays, `ArrayList`, or generic `List` objects - basically anything that has an iterative structure
	* The `for each` loop is much more simple in syntax - the general formula is: the variable, the colon (`:`), and the name of the data structure to iterate through
* A general rule of thumb is if you need to change the values of an existing data structure, `for` loops should be used to change the values and **not** `for each` loops because `for each` loops create a **copy** of the original data structure and iterates through that, instead of editing the original one

## Examples

# `for` loop and an array

```java
double[] raceTimes = {3.4, 5.6, 8.2, 3.9, 6.2, 5.8};
double min = raceTimes[0];

for (int i = 0; i < raceTimes.length; i++) {
	if (raceTimes[i] < min) min = raceTimes[i];
}

System.out.println(“The shortest time was “ + min);
```

# `for each` loop and an `ArrayList`

```java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(new Integer(5));
list.add(new Integer(10));
list.add(new Integer(12));

for (Integer i : list) {
	if (i.intValue() % 2 == 0) {
		System.out.println(“The value at index “ + i + “ is even”);
	}
}
```