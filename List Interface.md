# List Interface

Data structures like the `ArrayList` have overriden methods that are derived from the `List` interface. Because `List` is an interface, it is not possible to instantiate it, but it is possible to declare a reference to the `List` interface, as shown below.

```java
# Not possible
List<Integer> list = new List<Integer>();

# Possible
List<Integer> list = new ArrayList<Integer>();
```

Important methods that belong to the `List` interface:
* `add(E element)` - adds the object to the end of the list
* `add(int index, E element)` - adds the object to the specified index in the list
* `clear` - removes all the elements from the list
* `equals(Object o)` - compares the element in the parameter to an element inside of the list
* `get(int index)` - retrieves the object at the specified index
* `isEmpty` - confirms whether there is or is not an element inside of the list
* `remove(int index)` - removes the object at the specified index
* `remove(Object o)` - removes the first occurrence of the object in the list, provided that the object is actually in the list
* `set(int index, E element)` - sets the element present in the current index to the object passed into the parameter
