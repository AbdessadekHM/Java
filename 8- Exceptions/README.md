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

}
```






    


