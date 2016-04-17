# File IO

## Overview
* File IO, also known as File Input and Output, is used to read in a file and do something with the contents
* There are multiple packages that must be imported, such as:
    * `java.util.Scanner` - reads the file into our program
    * `java.io.IOException` - handles IO-related exceptions
    * `java.io.File` - the actual file object
* It is common to use the `hasNext()` method from the `Scanner` class with a `while` loop to loop through the contents of a File
* In order for File IO to work correctly, make sure that the path to your `txt` file is properly configured
    * In Eclipse, it should be outside of the `src` folder and inside the project folder

## Example

### Basic `txt` file output

`numbers.txt`
```
14
22
42
53
28
87
```

`IOTest.java`
```java
import java.util.Scanner;
import java.io.IOException;
import java.io.File;

public class IOTest {
    public static void main(String[] args) {
        Scanner in = null;
        try {
            in = new Scanner(new File("numbers.txt"));
            while (in.hasNext()) {
                System.out.println(in.nextLine());
            }
        } catch (IOException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

### Mean calculator

`numbers.txt`
```
128.5
380.4
123.9
684.2
679.4
189.5
948.2
```

`IOTest.java`
```java
import java.util.Scanner;
import java.io.IOException;
import java.io.File;

public class IOTest {
    public static void main(String[] args) {
        Scanner in = null;
        double sum = 0;
        double total = 0;

        try {
            in = new Scanner(new File("numbers.txt"));
            while (in.hasNextDouble()) {
                sum += in.nextDouble();
                total++;
            }
            System.out.println("Mean: " + sum/total);
        } catch (IOException e) {
            System.out.println(e.getMessage());
        }
    }
}
```
