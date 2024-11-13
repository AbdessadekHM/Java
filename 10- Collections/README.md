

# Colllections


## Overview: 

![image_4](../assets/4.png)

## The Need For Iterables:
When creating a class that we need to iterate over it, we can't do that by a loop, or we should change the list modifier inside the class to public, and use it directly which make our application more dependent to that class; if we want to change the list type our application is gonna break, because it accessing that list directly, but if that class uses Iterables interface we can loop over it.

## The Iterable Interface:

The Iterable Interface have 3 methods, 2 default methods, and one required method which `iterator()`.
> You can check the documentation for more informations
**Example**:

```java
public class className<T> implements Iterable<T>{
    //Instructions
    @Override
    public Iterator<T> iterator(){
        //...
    }
}
```
## The Iterator Interface:

The Iterator Interface having 4 methods(check documentation), two methods are required which are `hasNext()` & `next()`.

**Example**:
```java
// GenericList.java
package com.app.generics;

import java.util.Iterator;

public class GenericList<T> implements Iterable<T>  {

    @SuppressWarnings("unchecked")
    private T[] items = (T[]) new Object[10];

    private int count;

    public void add(T element) {
        items[count++] = element;
    }

    public T get(int index) {
        return items[index];
    }

    @Override
    public Iterator<T> iterator() {
        return new ListIterator(this);

    }

    private class ListIterator implements Iterator<T>{
        private GenericList<T> list;
        private int index;

        public ListIterator(GenericList<T> list){
            this.list = list;

        }

        @Override
        public boolean hasNext() {
            return (index < list.count);
        }

        @Override
        public T next() {
            return list.items[index++];
        }

        
    }

}
```


```java
//Main.java

package com.app;

import com.app.generics.GenericList;

public class Main {
    public static void main(String[] args) {
        var list = new GenericList<String>();
        list.add("one");
        list.add("one");
        list.add("one");
        list.add("one");
        list.add("one");
        list.add("one");
        list.add("one");
        list.add("one");
        
        System.out.println("line 17");
        for (var current : list) {

            System.out.println("line 20");
            System.out.println(current);
        }
        
        System.out.println("line 21");

    }
}
```

