# Variable Scope

## Overview
* There are two namespaces for variables, `global` and `local`
* Global variables are usually declared as `class` variables
* Local variables are usually declared within individual methods, or even conditional or iterative statements
* As long as they do not conflict, global and local variables can share the same name and object type/primitive data type
* For local variables, there is some memory that is allocated for them in the beginning of a parameter list or method, but then that memory is deleted once the reading of the parameter list or method has completed - the variable effectively does not *exist* anymore

## Example

All three of these variables can coexist within the program.

```java
public class Test {
    private int num = 10;

    private void testerMethod(int num) {
        return num;
    }

    public static void main(String[] args) {
        for (int num = 0; num < 10; num++) {
            System.out.println(num);
        }
    }

}
```
