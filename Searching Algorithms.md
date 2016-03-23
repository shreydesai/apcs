# Searching Algorithms

## Linear Search

**Overview:**
* This methods examines each element in sequence starting with the first one to determine if a target element is found; the loop will break if the target is found
* If the target is not found, then the method will output `-1`
* When searching an array of objects, one can use the `equal` method to compare the objects, such as Strings

**Code:**
```java
public static int linearSearch (Rectangle [] r) {
  for (int i = 0; i < r.length; i++) {
      if (r[i].myWidth == 4) {
          return i;
          }
      }
  return -1;
}
```
