
- [3- Control Flow](#3--control-flow)
  - [Comparison Opeartors](#comparison-opeartors)
  - [Logical Operator:](#logical-operator)
  - [If Statements:](#if-statements)
  - [Simplifying the If Statement:](#simplifying-the-if-statement)
  - [The Ternary Operator:](#the-ternary-operator)
  - [Switch Statements:](#switch-statements)
  - [For Loops:](#for-loops)
  - [While Loops:](#while-loops)
  - [Do..While](#dowhile)
  - [Break and Continue](#break-and-continue)
  - [For Each Loop](#for-each-loop)

# 3- Control Flow

## Comparison Opeartors 
comparison operators in java are same operators of other languages like javascript, C ...

| Operator | Description                         |
|----------|-------------------------------------|
| `==`     | Equal to                            |
| `!=`     | Not equal to                        |
| `>`      | Greater than                        |
| `<`      | Less than                           |
| `>=`     | Greater than or equal to            |
| `<=`     | Less than or equal to               |

## Logical Operator:

| Operator | Description                                      |
|----------|--------------------------------------------------|
| `&&`     | Logical AND (returns true if both conditions are true) |
| `||`     | Logical OR (returns true if at least one condition is true) |
| `!`      | Logical NOT (reverses the logical state of its operand) |
| `&`      | Bitwise AND (operates at the bit level; can also be used as logical AND without short-circuiting) |
| `|`      | Bitwise OR (operates at the bit level; can also be used as logical OR without short-circuiting) |

> for `&&`if the first expression is false it doesn't evaluate the next one, and for `||` if the first expression is true it doesn't evaluate the next one.
> but for `&` and `|` they always evaluate both sides if they are used as logical operators

## If Statements:

**Syntaxe:**
```java
if (condition) {
    //instructions
}
else if (condition) {
    //instuctions
}
else{
    //instruction
}
//but note that if instructions have just one line, we have the choice the not set the curley braces
if (condition)
    //instruction
else 
    //instruction
```
## Simplifying the If Statement:

we can also return a false or true from a condition without if statements

**Example:**
```java
int Income = 5000;
boolean hasHighIncome = (Income > 4000); //true
```

## The Ternary Operator:
the `Ternary` Operator is come to simplify the if statement and add syntaxe sugar.

**Syntaxe:**
```java
int age = 6;
String classroom = age < 6 ? "First" : "Second"; //Second 
```
## Switch Statements:
Switch has the same base as if statements.

**Syntaxe:**

```java
switch (variable){
    case value_1:
        //instructions
        break;
    case value_2:
        //instructions
        break;
    default:
        //instructions

}
```
> It's important to use break statement in cases, because java one it found the right case it continue execute other cases even if they are false.

## For Loops:

**Syntaxe:**

```java
for (int i = 0; i < 5; i++){
    //instuctions
}
```

> As we mentioned before in if statements, when having one instruction we have the choice to remove {}


## While Loops:

**Syntaxe:**

```java
while (condition){
    //instructions
}
```
**Example:**

```java
package org.example;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        String input = "";
        Scanner scanner = new Scanner(System.in);
        while(!input.equals("quit")) {
            System.out.print("Input: ");
            input = scanner.next().toLowerCase();
            System.out.println(input);
        }
        }
    }

```
## Do..While

The difference between while loop and do..while loop, is in do..while loop the code is executed at least one time.

**Syntaxe:**

```java
do{
    //instruction
}while(condition)
```

**Example:**

```java
//same program in while loop's example
do {
    System.out.print("Input: ");
    input = scanner.next().toLowerCase();
    System.out.println(input);
}while(!input.equals("quit"));
```
## Break and Continue
- `break` statement is used to break a loop 
- `continue` statement is used to skip an instance of a loop

**Syntaxe:**

```java
while(true){
    //instructions + condition
    continue;
    //condition
    break;
}
```
## For Each Loop

**Syntaxe:**

```java
for (type name: array_name) { //in the name variable, it will be stored one array_name item per iteration
    //instructions
}
```

**Example:**

```java
String[] fruits = {"Apple", "Banana", "Orange", "Strawberry"};

for(String fruit : fruits)
    System.out.println(fruit);
```
