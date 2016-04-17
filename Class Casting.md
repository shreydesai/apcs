# Class Casting

## Overview
* Class casting is to refer to the methods or variables of a sub class in reference to its parent class
* If a child class inherits from a parent class, but the child class has additional methods NOT included in the parent class, then class casting must be used when initializing a variable with polymorphic behavior
* The general formula for casting is: `((class name) variable name)<method>`

## Example

Because the `Student` class has methods that the `Person` class does not have, when declaring a `Student` variable with polymorphic behavior, the variable must use class casting.

```java
public class Person {
    public String name = "Person";
    public boolean female = true;

    public String getName() {
        return name;
    }

    public boolean isFemale() {
        return female;
    }
}

public class Student extends Person {
    public int[] grades = {90, 92, 96, 95};

    public int[] getGrades() {
        return grades;
    }
}

public class Driver {
    public static void main(String[] args) {

        // Need to use class casting because the Person
        // class does not have the getGrades method
        Person p = new Student();
        ((Student) p).getGrades();

        // Don't need to use class casting because the
        // reference is to Student, not Person
        Student s = new Student();
        s.getGrades();
    }
}
```
