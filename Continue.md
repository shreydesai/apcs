# Continue

## Overview

* The `continue` keyword is used for skipping over something - this is mostly used in a `for` or `while` loop where you iterate over a set or sets of elements

## Example

```java
String test = “The fox jumped over the cat”;

for (int i = 0; i < test.length(); i++) {
	if (test.charAt(i).equals(“e”) {
		continue;
	} else {
		System.out.println(test.charAt(i));
	}
}
```

Note: This snippet of code will print out all of the characters in the `test` variable except for the `e` characters. The `continue` keyword is used here to skip over these characters.