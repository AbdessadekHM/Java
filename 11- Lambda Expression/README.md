# Lambda Expressoin:

## Functional Interfaces:

`Functional Interfaces`: are interfaces that have a single abstract method(doesn't have an implementation in the Interface).

**Exemple**:
```java
package com.app.lambdas;

Interface Printer{
    void print(String message);
    default String defaultMethod(){
        //Instructions
    
}
```
## Anonymous Classes:

Anonymous Classes are classes that are created inside another class without a name like :
```java
greet(new Printer(){
    @Override
    public void print(String message){
        System.out.print(message);
    }
});
//greet is a method that takes as argument a Printer object, so we created a direct class who implement Printer
```

## Lambda Expression:
`Lambda Expression` allow us to declare a function(anonymous function).

**Example**:
```java
greet((String message) -> {
    System.out.print(message);
});
// greet function takes in argument a Printer implementation which a functional interface, it has one method to be overrided, and it's the same method we declare using lambda expression
greet(message -> System.out.print(message));
// we can skip type declaring, because java compiler directly understand that we are impelemting the print function from Printer, and it knows its signature

Printer printer = message -> System.out.print(message);
greet(printer);
// we can store lambda expression in a variable 
```
## Variable Capture:

When using Lambda function, we still access to variable inside the method we use the expression in, or even class fields.


