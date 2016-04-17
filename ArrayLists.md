# **ArrayLists**
- can only hold objects
- stores a list of elements and provides methods to find, insert, and remove an element
- an ArrayList object contains an array of object references plus many methods for managing that array

## Some ArrayLists Methods
- .get()
- .add(object o)
- .size()
- .remove()
  + returns the removed object
- set(int i, object o)

## Example Code
``` javascript
ArrayList <String> colorList = new ArrayList <String> ();
colorList.add("green");
colorList.add("white");
colorList.add("yellow");

//returns the size or length of the ArrayList colorList
colorList.size();

//makes index 0 the String "red"
colorList.set(0, "red");

//removes the object at index 2 of colorList, 
//but returns the object that was at index 2
colorList.remove(2);

//gets the object at index 1
colorList.get(1);

//adds the String "blue" at index 2 of colorList
colorList.add(2, "blue");
```
