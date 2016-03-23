# Searching Algorithms

## Linear Search

```java
public static int linearSearch (Rectangle [] r){

  for (int i = 0; i < r.length; i++){
      if (r[i].myWidth == 4){
          return i;
          }
      }
      
  return -1;
  
}
```
