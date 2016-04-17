# **CompareTo Method**
- returns three different values: negative, positive, and equal values
- To determine whether something is greater than another, a left to right approach is useful
- one-line return statements are useful for compareTo() methods, but one must ensure that the correct primitive data type is being returned.

## Example Code
``` javascript
public int compareTo (int i){
  if ( i < [other number]){
    return -1;
  }
  if ( i > [other number]){
    return 1;
  }
  if ( i == [other number]){
    return 0;
  }
}

int x = 2;
int y = 7;

if (x.compareTo(y) > 0){
    System.out.println("x is greater than y");
}
if (x.compareTo(y) < 0){
    System.out.println("x is less than y");
}
if (x.compareTo(y) == 0){
    System.out.println("x is equal to y");
}
```

# **EqualsTo Method**
- compares the contents of an object to check if they are equal to each other
- The method itself is usually a function in the class it is defined in. 

## Example Code
``` javascript
public boolean equals (int i){
  return ((test1+test2+test3) == (s.test1+s.test2+s.test3))
}
```

