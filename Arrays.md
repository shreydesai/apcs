# Arrays

## Overview
* Arrays are the most basic data structure in Java
* Arrays are linear - they store elements in a side-by-side format

Consider you have a set of numbers like `1, 4, 6, 2, 9`. Below is a visual representation of how an array would store this set:

```java
_____________________
|   |	|   |   |   |
| 1 | 4	| 6 | 2 | 9 |
|___|___|___|___|___|
```

* Arrays can hold both primitive data types and objects
	* `int` and `double` arrays will have `0` as their default value
	* `Object` arrays will have `null` as their default value - this means trying to access a value of an `Object` array without declaring it will throw a `NullPointerException`
* The length of an array can be retrieved with the `length` attribute
* Ways to declare an array
	* First way: `<type>[] <name> = new <type>[<size>];`
	* Second way: `<type>[] <name> = {<item 1>, <item 2>, <item n>};`

## Examples

### `int` array

```java
int[] array = new int[10];

for (int i = 0; i < array.length; i++) {
	array[i] = i;
}
```

### `String` array

```java
String target = “Mike”;

String[] array = {“Jack”, “Jill”, “Bob”, “Henry”, “Mike”, “James”};
for (String s : array) {
	if (s.equals(target)) {
		System.out.println(target + “ was found!”);
		break;
	}
}
```
