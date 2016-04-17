# Wrapper Classes

## Overview
* Because some data structures like `ArrayList` require objects, we must use wrapper classes for the primitive data types
    * We can do `int[] num`, but we can't do `List<int>`
* Each primitive data type has a corresponding wrapper class - you just capitalize the first letter of each
    * `int` -> `Integer`
    * `double` -> `Double`
    * `boolean` -> `Boolean`
* The wrapper classes are objects, so in order to *unpack* the value inside, use its respective method
    * `Integer` -> `getIntValue()`
    * `Double` -> `getDoubleValue()`
    * `Boolean` -> `getBooleanValue()`
* You can also use wrapper classes with arrays, such as `Integer[] nums` instead of `int[] nums` - it just becomes an object array

## Example

Random number generation, storing the values in an `ArrayList`, and iterating through it to calculate the mean.

```java

import java.util.ArrayList;

public class Test {
    public static void main(String[] args) {
        ArrayList<Integer> values = new ArrayList<Integer>();
        int total = 0;
        for (int i = 0; i < 100; i++) {
            int num = (int) (Math.random() * 100);
            values.add(new Integer(num));
        }
        for (Integer i : values) {
            int num = i.getIntValue();
            total += num;
        }
        System.out.println("Mean: " + values.size()/num);
    }
}

```
