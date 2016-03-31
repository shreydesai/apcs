# Object-Oriented Programming

## Overview

* Object-oriented programming (OOP) is a standard by which programming languages can model  objects in the world
* **Classes** represent objects and **methods** can be used to do something to the object
* Objects also have attributes, which can be represented by individual variables

## Attributes
* Represented by variables, which can be primitive data types or even other objects, like the `String` class
* Generally declared as `private` but they can also be `public` – the difference is whether they can be accessed from within or outside of the class
	* `private` attributes can only be used inside the class
	* `public` attributes can be used by classes from the outside

```java
// How to declare variables
private boolean x1;
private int x2;
private double x3;
```

## Methods
* Represent functions that the object either has or can do
* For example, a `Square` object could have methods called `getArea()` and `getPerimeter()` that calculate the area and perimeter of the `Square`
* `return` is used to essentially return or "get" a value from the function; if you have nothing to return, then put `void` in the identifier of the function
	* If you use `return`, you must declare the primitive data type or object that the function is returning in the identifier

```java
// How to declare methods

// Example of the return keyword
private double getArea() {
	return height * width;
}

// Example of the void keyword
private void sayHello() {
	System.out.println("Hello from this method");
}
```

## Methods and Parameters

* Parameters are used in methods in order to pass a value into the function for its internal use
	* Each parameter requires declaring it with its data type and name, just like a variable or class attribute is declared 
* For example, we need the height and width of a rectangle in order to calculate its area, so these can be parameters in a function called `getRectangleArea()`

```java
private double getRectangleArea(double height, double width) {
	return height * width;
}
```

## Constructor

* The constructor is a special method used to instantiate the attributes of a class
* For example, we cannot know what a `Square` fundamentally and intrinsically is without knowing its height and width, which is why these attributes are absolutely necessary
* How constructors are different from methods
	* They do not return anything
	* Their name must be the same as the class name
	* They do not have additional identifiers like `void` or `static`

```java
public class Square {
	
	// Attributes
	private double height;
	private double width;

	// Constructor
	public Square(double myHeight, double myWidth) {
		height = myHeight; // copy parameter into attribute
		width = myWidth; // copy parameter into attribute
	}
}
```

## Case Study: Pencil

A pencil is an example of an object in the real world. Naming a class can follow this general formula: `public class <class name>`. Note: there are no other modifiers that go in the class declaration.

```java
public class Pencil {
	// Attributes and methods go here
}
```

Examples of attributes that belong to a pencil include a serial number, lead width, and whether it is a mechanical pencil or regular pencil.

```java
public class Pencil {
	
	private long serialNumber;
	private double leadWidth;
	private boolean isMechanical;
}
```

A constructor can also be used to instantiate these variables.

```java
public class Pencil {
	
	private long serialNumber;
	private double leadWidth;
	private boolean isMechanical;
	
	public Pencil(long mySerialNumber, double myLeadWidth, boolean myIsMechanical) {
		serialNumber = mySerialNumber;
		leadWidth = myLeadWidth;
		isMechanical = myIsMechanical;
	}
}
```

We can also add methods in order to access the private data members or attributes if we want to use the `Pencil` object in another class. Note that all of the methods are uniform and specific in their name.

```java
public class Pencil {
	
	private long serialNumber;
	private double leadWidth;
	private boolean isMechanical;
	
	public Pencil(long mySerialNumber, double myLeadWidth, boolean myIsMechanical) {
		serialNumber = mySerialNumber;
		leadWidth = myLeadWidth;
		isMechanical = myIsMechanical;
	}
	
	public long getSerialNumber() {
		return serialNumber;
	}
	
	public double getLeadWidth() {
		return leadWidth;
	}
	
	public boolean getMechanical() {
		return isMechanical;
	}
}
```