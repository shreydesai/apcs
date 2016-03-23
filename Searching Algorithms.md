# Searching Algorithms

## Linear Search

**Overview:**
* This methods examines each element in sequence starting with the first one to determine if a target element is found; the loop will break if the target is found
* If the target is not found, then the method will output `-1`
* When searching an array of objects, one can use the `equal` method to compare the objects, such as Strings
* Time complexity is O(n), or linear, which is considered inefficient

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

## Binary Search

**Overview:**
* Binary search divides an array in half and examines the data at the point of the split. When the array is split, it is easy to rule out the half that does not matter
* Steps include: 1) Divide the array in half 2) Examine the value in the middle; is the value you’re searching for higher or lower? If higher, discard the lower half array. If lower, discard the higher half array. 3) Repeat.
* **Important consideration:** Arrays must be sorted in order for binary search to work. Its time complexity does not account for its pre-processing time.
* Time complexity is O(log2N), or logarithmic, so it is considered quite efficient. For example, finding the number `1` in a list of `1024` would take `10` steps, since `log2(1024)` is equal to `10`.

**Non-Recursive Code:**
```java
int[] data;
int size;

public boolean binarySearch(int key) {
    int low = 0;
    int high = size - 1;

    while (high >= low) {
        int middle = (low + high) / 2;
        if (data[middle] == key) {
            return true;
        }
        if (data[middle] < key) {
            low = middle + 1;
        }
        if (data[middle] > key) {
            high = middle - 1;
        }
    }

    return false;
}
```

**Recursive Code:**
```java
public int binarySearch(int[] list, int lowIndex, int highIndex, int value) {
    if (lowIndex > highIndex) {
        return -1;
    } else {
        int middle = (lowIndex + highIndex) / 2;
        if (value == list[middle]) {
            return middle;
        } else if (value < list[middle]) {
            return binarySearch(list, lowIndex, middle - 1, value);
        } else {
            return binarySearch(list, middle + 1, highIndex, value);
        }
    }
}
```

Note: The recursive solution is sometimes easier to understand, but might be less efficient when compared to the non-recursive solution because it requires more memory to add each call to the recursive stack. However, both solutions are conceptually equivalent.
