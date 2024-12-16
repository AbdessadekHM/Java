# Streams

## Imperative vs Functional programming 

- **Imperative**: a style programming, where we have statements that specifies how something should be done.
- **Declarative**: specifiy what should be done like (sql).
- **Functional**: it's a type of declarative programming, but it does add some additional concepts.

- **Streams**: is a sequence of objects, but it doesn't store data as collections, but it's just a way to get data out of the collection(by chunks)

**Example**:
```java
package com.app.streams;

import java.util.List;

public class StreamsDemo {

    
   public static void show(){
      List<Movie> movies = List.of(
         new Movie("a", 10),
         new Movie("b", 20),
         new Movie("c", 30),
         new Movie("d", 9)
      );
      // imperative programming
      int count = 0;

      for( Movie movie: movies)
         if(movie.getLikes()>= 10)
            count++;

      count = 0;
     // Declarative Programming
     
      count = (int) movies.stream().filter(movie-> movie.getLikes()>=10).count();
      System.out.println(count);
      

   } 
}
```


## Creating Streams
We can create streams : 
   - from collections
   - from arrays
   - from arbiratry objects
   - infinite/finite streams

### Creating Streams from collections

**Syntaxe**:
```java
List<Movie> movies = ...
movies.stream() // return a stream
```

### Creating Streams from arrays

**Syntaxe**:
```java
int[] i = new int[20];

// java.util.Arrays
Arrays.stream(i)

```

### Creating Streams from arbiratry objects 

**Syntaxe**:
```java
package com.app.streams;

import java.util.stream.Stream;

public class StreamsDemo {

    
   public static void show(){

      Stream<String> chars = Stream.of("a","b","c","d","e");
      chars.forEach(n -> System.out.println(n));

   } 
}
```

### Creating Infinite/Finite Streams
using generate
**Syntaxe**:
```java
package com.app.streams;

import java.util.stream.Stream;

public class StreamsDemo {

    
   public static void show(){

      Stream<Double> numbers = Stream.generate(()->  Math.random()* 10);

      numbers.forEach(n->System.out.println(n));


   } 
}
```
we can add limits 
```java

numbers.limit(3).forEach(n->System.out.println(n));

```
using `iterate`

**Syntaxe**:

```java
Stream<Integer> numbers = Stream.iterate(1,n->n+1);

numbers.limit(3).forEach(n->System.out.println(n));
```
## Mapping Elements

`map` it's a stream method that takes a function as argument

**Example**
```java
package com.app.streams;

import java.util.List;

public class StreamsDemo {

    
   public static void show(){

      List<Movie> movies = List.of(
         new Movie("a",10),
         new Movie("b",10),
         new Movie("c",10),
         new Movie("d",50),
         new Movie("e",10),
         new Movie("f",30)
      );

      movies
      .stream()
      .map(movie -> movie.getTitle())
      .forEach(title -> System.out.println(title));


   } 
}
```

mapToInt:

```java
movies
.stream()
.mapToInt(movie -> movie.getLikes())
.forEach(title -> System.out.println(title));
```

**Flat**
it's a useful method for matrix reading.

**Example**
```java
Stream<List<Integer>> numbers = Stream.of(List.of(1,2,3), List.of(4,5,6));

numbers
   .forEach(item -> System.out.println(item)); // (1,2,3) (4,5,6)
      
numbers
   .flatMap(list -> list.stream())
   .forEach(item -> System.out.println(item)); // 1,2,3,4,5

```

## Filter Elements 

Stream methods generally are two types: 
   - Intermediate Methods: are methods that return a new form of stream like map, filter... 
   - Terminal Streams: are methods that are void or doesn't return a stream like forEach

Filter:
it's a stream method that return a filtered form of the giving stream, and it does take `Predicate` as argument

**Syntaxe**
```java
Stream.filter(Predicate); // it does return a stream
```

**Example**
```java
List<Movie> movies = List.of(
   new Movie("1", 1),
   new Movie("2", 2),
   new Movie("3", 3),
   new Movie("4", 13),
   new Movie("5", 15),
   new Movie("6", 16)
);


Predicate<Movie> isPopular = m -> m.getLikes() > 10;
Consumer<String> print = m -> System.out.println(m);

System.out.println("start");
movies.stream()
   .filter(isPopular)
   .map(m -> m.getTitle())
   .forEach(print);

```


## Slicing Stream

In Stream slicing we have four main methods:
```java
streamInstance.limit(long a) // it does return a elementing, start counting from the first element
streamInstance.skip(long a) // it does skip a elements so return a stream from a element to the last one
streamInstance.takewhile(Predicate) // it does stop in the element that doesn't much the predicate
streamInstance.dropwhile(Predicate) // the inverse of takeWhile method
```

**Example**:
```java
List<Movie> movies = List.of(
   new Movie("1", 1),
   new Movie("2", 2),
   new Movie("3", 3),
   new Movie("4", 13),
   new Movie("5", 15),
   new Movie("6", 16)
);



```

## Sorting Elements
It has two methods(overload sorts):

**Example**

```java
List<Movie> movies = List.of(
   new Movie("1", 1),
   new Movie("4", 13),
   new Movie("3", 3),
   new Movie("6", 16),
   new Movie("5", 15),
   new Movie("2", 2)
);


movies.stream().sorted().forEach(m -> System.out.println(m.getTitle()));; // to use this we should implement Comparable interface in Movie class
System.out.println("\n");

movies.stream().sorted((a,b) -> a.getTitle().compareTo(b.getTitle())).forEach(m -> System.out.println(m.getTitle()));;
System.out.println("\n");
movies.stream().sorted(Comparator.comparing(m -> m.getTitle())).forEach(m -> System.out.println(m.getTitle()));;
System.out.println("\n");
movies.stream().sorted(Comparator.comparing(Movie::getTitle)).forEach(m -> System.out.println(m.getTitle()));;
System.out.println("\n");
//sort in reverse order
movies.stream().sorted(Comparator.comparing(Movie::getTitle).reversed()).forEach(m -> System.out.println(m.getTitle()));;
```




















