# Exceptions

## What Are Exceptions:
Exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions.


`Stack Trace`: when an exception is throwen, it shows the called methods in reverse order.

## Types of Exceptions:
- **Checked Exceptions(Compile time)**: are exceptions that we should handle, like reading data from a file etc...
- **Unchecked Exceptions(Run time)**: are exceptions that we don't need to handle them, because they are came from programming mistakes.
    Examples: 
        - NullPointerException
        - ArithmeticException
        - IllegalArgumentException
        - IndexOutOfBoundException
        - IllegalStateException
- **Errors**: are exceptions related to ressources or jvm itself, we can't not handle it at all, like `StackOverFlow`.
  
## Exceptions Hierarchy:

![image_3](../assets/3.png)

## Catching Exceptions:

**Syntaxe:**
```java
package com.app.exceptions;

import java.io.FileReader;
import java.io.IOException;

public class ExceptionsDemo {

    public static void show(String message) {
        try (var reader = new FileReader("file.txt")) {
        } catch (IOException e) {
            System.out.println(e.getMessage());
            e.printStackTrace();
        }

        System.out.println("out of block");

    }
    //or we can use for try instead of try(instruction)
    try{
        //INSTRUCTION
    }
    /*
        The difference between the two implementation, is in the first reader object is gonna automatically closed after finishing the block.
        where the second we should close reader manually, by creating a null object, and affect it inside try, closing it using finally clausure 
    */

}
```

## Catching Multiple Exceptions: 

```java
package com.app.exceptions;

import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class ExceptionsDemo {

    public static void show(String message) {
        try (var reader = new FileReader("text.txt")) {
            new SimpleDateFormat().parse(null);
        } catch (FileNotFoundException e) {
            System.out.println(e.getMessage());
            e.printStackTrace();

        } catch (ParseException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();

        }
        System.out.println("out of block");

    }

} 
// or
        try (var reader = new FileReader("text.txt")) {
            new SimpleDateFormat().parse(null);
        } catch (FileNotFoundException e) {
            System.out.println(e.getMessage());
            e.printStackTrace();

        } catch (ParseException | IOException e) {
            e.printStackTrace();
        }
        System.out.println("out of block");
    
```

## The Finally Block: 
finally block is a block that's gonna run in both case try and catch.

```java
    public static void show(String message) {
        FileReader reader = null;
        try {
            reader = new FileReader("text.txt");
            new SimpleDateFormat().parse(null);
        } catch (FileNotFoundException e) {
            System.out.println(e.getMessage());
            e.printStackTrace();

        } catch (ParseException | IOException e) {
            e.printStackTrace();
        } finally {
            if (reader != null) {
                try {
                    reader.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }

        }
        System.out.println("out of block");

    }
```




    


