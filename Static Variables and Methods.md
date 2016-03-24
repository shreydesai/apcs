# Static Variables and Methods

## Overview

* Static variables and methods are used when you want to create variables that are common, or "static," for all objects
* Unlike instance variables, static variables usually remain constant or change minimally when objects are declared
* Static variables and methods should **not** access instance variables because this ruins the purpose of them being class-specific - this means you can't use the `this` keyword when referring to static variables and methods
* For example, variables like `color` or `size` would fluctuate for a `Frog` object, but something like `pondColor` or `pondSize` would probably remain constant between `Frog` objects

## Declaration

Static variables and methods are declared using the `static` modifier, along with the other modifiers. The `static` declaration should come after visibility modifiers and before return type modifiers.

```java
# Example of a static variable
private static int number;

# Example of a static method
private static int getNumber() {
    return number;
}
```

## Calling static variables

Because static variables and methods are a part of the class, they must be called by referring to the class itself, and not the object. For example, recalling the `Frog` class from above:

```java
# Access the pondColor variable
Frog.pondColor;

# Access the pondColor variable through an accessor method
Frog.getPondColor();
```

While it is possible to access static variables and methods through an object, this is discouraged because it defeats the purpose of the variable/method being a part of the class itself.
