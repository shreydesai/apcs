# Sorting Algorithms

## Bubble Sort

**Overview:**
* Elements are sorted as they gradually "bubble" to their proper location in the array
* The algorithm continues by comparing adjacent elements of an array; the first and second elements are compared and swapped if out of order
* There is an early kick-out feature, which exits the array if there are no swaps that have been made (generally uses a `while` loop)
* Time complexity is O(n^2), or quadratic time; the algorithm is considered inefficient because it uses nested loops

**Code:**
```java
public void bubbleSort(int[] list) {
    for (int outer = 0; outer < list.length - 1; outer++) {
        for (int inner = 0; i < list.length - outer - 1; inner++) {
            if (list[inner] < list[inner + 1]) {
                int temp = list[inner];
                list[inner] = list[inner + 1];
                list[inner + 1] = temp;
            }
        }
    }
}
```

Note: The `<` in the first conditional statement can be changed to `>` if you want to change the algorithm to sort the elements in an ascending order (lower elements to higher elements).

There is also a more efficient version of the bubble sort algorithm. In the previous example, it continues throughout the entire array until all elements have been touched. In the more efficient version, the algorithm will make up to `n - 1` passes, but will exit early if no exchanges are made on the previous pass.

```java
public static void bubbleSort(int[] list) {
    int k = 0;
    boolean exchangeMade = true;

    while ((k < list.length - 1) && exchangeMade) {
        exchangeMade = false;
        k++;
        for (int j = 0; j < list.length - k; j++) {
            if (list[j] < list[j + 1]) {
                swap(a, j, j + 1);
                exchangeMade = true;
            }
        }
    }
}
```

## Selection Sort

**Overview:**
* The selection sort is a combination of searching and sorting
* During each iteration, the unsorted element with the smallest/largest value is moved to its respective index in the array
* The inner loop finds the smallest/largest value and the outer loop places the value into its respective index
* There are `n - 1` iterations where `n` is the length of the array
* Time complexity is O(n^2), or quadratic time; the algorithm is considered inefficient because it uses nested loops.

**Code:**

```java
public void selectionSort(int[] list) {
    for (int i = 0; i < list.length - 1; i++) {
        int minIndex = findMinimum(list, i);
        if (minIndex != i) {
            swap(a, i, minIndex);
        }
    }
}

public int findMinimum(int[] list, int first) {
    int minIndex = first;
    for (int i = first + 1; i < list.length; i++) {
        if (list[i] < list[minIndex]) {
            minIndex = i;
        }
    }
    return minIndex;
}

public void swap(int[] list, int x, int y) {
    int temp = list[x];
    list[x] = list[y];
    list[y] = temp;
}
```

## Insertion Sort

**Overview:**
* This algorithm passes through the array only once by splitting the array into two-sub arrays, and then working with both of them
* The first sub-array is always sorted and increases in size as the sort continues; the second sub-array is unsorted and decreases in size as the elements are inserted into the first sub-array
* Unlike the other algorithms, insertion sort has a `k` value, or "key", which 1) stands for the element that needs to be sorted and 2) indicates the division between the first and second sub-arrays
* The goal is that on the `kth` pass, the `kth` element will be sorted

**Code:**
```java
public void insertionSort(int[] list) {
    int itemToInsert, j;
    boolean stillLooking;

    for (int k = 1; k < list.length; k++) {
        itemToInsert = list[k];
        j = k - 1;
        stillLooking = true;

        while ((j >= 0) && stillLooking) {
            if (itemToInsert < list[j]) {
                list[j + 1] = list[j];
                j--;
            }
            else {
                stillLooking = false;
            }
        }
        
        list[j + 1] = itemToInsert;
    }
}
```

## Sorting Objects

**Overview:**
* Java objects will generally implement the `Comparable` interface and implement the method `compareTo`, which allows for the testing of integers or floating-point numbers
* The goal is to replace all of the array parameters with the respective object and use `compareTo` instead of mere array item comparison with numerical operators

**Sample Code:**
```java
public int findMinimum(Object[] list, int first) {
    int minIndex = first;

    for (int i = first + 1; i < list.length; i++) {
        if ((Comparable)list[i]).compareTo([list[minIndex]] < 0) {
            minIndex = i;
        }
    }

    return minIndex;
}
```
