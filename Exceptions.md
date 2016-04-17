# Exceptions

## Overview
* Exceptions occur when there is an error that Java detects in your program during compile or run time
* While you cannot prevent exceptions from occurring (in some situations), you can control the outcome
* The general strategy to control exceptions is using a `try`/`catch` block, where you `try` to perform a block of code, but you can `catch` the exception if it occurs
* You must specify what type of exception you're "catching" in the `catch` block - the most generic one is `Exception`, but sometimes programmers will put more specific ones like `FileNotFound`

## Example

### Handling a `NullPointerException`
```java
public class Student {

    private String name;

    public Student(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        Student s = new Student(null);

        try {
            System.out.println(s.name);
        } catch (NullPointerException e) {
            System.out.println("The variable is null");
        }
    }
}
```

### Handling an `ArrayIndexOutOfBounds` Exception

```java
public static void main(String[] args) {
    int[] array = {0, 0, 0, 0, 0, 0};
    int i;

    try {
        for (i = 0; i <= array.length; i++) {
            System.out.println(array[i]);
        }
    } catch (ArrayIndexOutOfBounds e) {
        System.out.println("Index " + i + " does not exist");
    }
}
```
