# Sorting Algorithms

## Bubble Sort

**Overview:**
* Elements are sorted as they gradually "bubble" to their proper location in the array
* The algorithm continues by comparing adjacent elements of an array; the first and second elements are compared and swapped if out of order
* There is an early kick-out feature, which exits the array if there are no swaps that have been made (generally uses a `while` loop)
* Time complexity is `O(n^2)`, or quadratic time; the algorithm is considered inefficient because it uses nested loops

**Code:**
```java
public void bubbleSort(int[] list) {
    for (int outer = 0; outer < list.length - 1; outer++) {
        for (int inner = 0; i < list.length - outer - 1; inner++) {
            if (list[inner] < list[inner + 1]) { //this statement determines whether high-to-low
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
            if (list[j] < list[j + 1]) { //this statement determines whether high-to-low
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
* Time complexity is `O(n^2)`, or quadratic time; the algorithm is considered inefficient because it uses nested loops.

**Code (long version):**

```java
public void selectionSort(int[] list) {
    for (int i = 0; i < list.length - 1; i++) {
        int minIndex = findMinimum(list, i);
        if (minIndex != i) {
            swap(a, i, minIndex);
        }
    }
}

//if you want to do high-to-low, then you do findMaximum
//if you want to do low-to-high, then you do findMinimum
public int findMinimum(int[] list, int first) {
    int minIndex = first;
    for (int i = first + 1; i < list.length; i++) {
        if (list[i] < list[minIndex]) { //this statement determines whether high-to-low
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

**Code (short version):**
```java
public void selectionSort(int[] list) {
    int i, j, first, temp;

    for (i = list.length - 1; i > 0; i--) {
        first = 0;

        for (j = 1; j <= i; j++) {
            if (list[j] < list[first]) {
                first = j;
            }
        }

        temp = list[first];
        list[first] = list[i];
        list[i] = temp;
    }
}
```

## Insertion Sort

**Overview:**
* This algorithm passes through the array only once by splitting the array into two-sub arrays, and then working with both of them
* The first sub-array is always sorted and increases in size as the sort continues; the second sub-array is unsorted and decreases in size as the elements are inserted into the first sub-array
* Unlike the other algorithms, insertion sort has a `k` value, or "key", which 1) stands for the element that needs to be sorted and 2) indicates the division between the first and second sub-arrays
* The goal is that on the `kth` pass, the `kth` element will be sorted
* Time complexity is `O(n^2)`, or quadratic time; the algorithm is considered inefficient because it uses nested loops

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
            if (itemToInsert < list[j]) { //this statement determines whether high-to-low
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

## Merge Sort

**Overview:**
* In summary, the purpose of merge sort is to "divide and conquer"
* The list passed into the merge sort algorithm will be split into equal size lists, which will be sorted, and then **merged back** into the larger list, which will be sorted
* There are both non-recursive and recursive implementations
    * The **non-recursive** algorithm usually splits the algorithm into two sections – selection sort and a merge method
    * The **recursive** algorithm calls itself over and over again until the list is completely sorted
* Time complexity is `O(N * log2N)`, or linear logarithmic time; the algorithm is considered quite efficient, especially when compared to the quadratic time sorting algorithms

**Code (non-recursive pseudocode):**
```java
public void mergeSort(ArrayList<Integer> list, int first, int last) {
    int mid;

    mid = (first + last) / 2;
    selectionSort(list, first, mid);
    selectionSort(list, mid + 1, last);
    merge(list, first, mid, last);
}
```

**Code (recursive pseudocode):**
```java
public void mergeSort(int[] list, int first, int last) {
    int mid;

    if (first == last) {
        return;
    } else if (first + 1 == last) {
        // determine smaller/bigger and swap
    } else {
        mid = (first + last) / 2;
        mergeSort(list, first, mid);
        mergeSort(list, mid + 1, last);
        merge(list, first, mid, last);
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

## Identifying Algorithms

### General rule
Assuming `list[inner]` will be replaced with `list[inner + 1]`, `<` inside the boolean condition means **high to low** and `>` means **low to high**.

### Bubble Sort
* The non-early kickout feature has two `for` loops
* The early kickout feature has a `while` loop with a boolean condition
* The sorting happens inside the loops

### Selection Sort
* There are two `for` loops
* Inside the inner `for` loop, there is variable assignment
* Inside the outer `for` loop, there is sorting

### Insertion Sort
* There is one `for` loop and one `while` loop
* The `while` loop has a boolean condition
* Inside the `while` loop, there is a variable that decrements
* Sorting happens inside the outer loop