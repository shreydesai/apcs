# Importing

## Overview

* Programmers often need to use libraries that are included in the standard Java distribution and reference methods from other classes
* Libraries auto-imported include the `String` and `System` classes
* In order to import a library, you can use the `import` keyword
* In AP Computer Science, the classes that are imported the most include `ArrayList`, `Random`, `Scanner`, and `File`
* Follow these steps to import a class
	* Select the class you need to import, for example, a `Scanner`
	* Determine where it is stored - you can find this information easily from the Java documentation or online on websites like Stack Overflow
	* Write the import statement with the `import` keyword

## Example

```java
import java.util.Scanner;

public class ReadFile {
	
	// Create object variable
	Scanner in = new Scanner(System.in);
}
```