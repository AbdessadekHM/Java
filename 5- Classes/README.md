# Classes
Class is a blueprint to make objects, objects are instances of a class

## Create Classes:

**Syntaxe:**
```java
public class ClassName{
    public int attribute;
    private String attribute;
    public void addAttributes(String attribute){}
    ...
}
```
**Example:**
```java
package org.example;

public class TextBox {
    //it's better to initialize this attributes to avoid null problems
    public String text = "";

    public void setText(String text) {
        this.text = text;
    }
    public void clearText() {
        text = "";
    }
}

```

## Create Objects
As mentioned before *Objects* are instances of classes.

**Syntaxe:**

```java
ClassName objectName = new ClassName();
// OR 
var objectName = new ClassName();
```

**Example:**

```java
package org.example;

public class Main {
    public static void main(String[] args) {
        var textBox_1 = new TextBox();

        TextBox textBox_2 = new TextBox();

        System.out.println(textBox_1.text.toUpperCase());
        textBox_1.setText("hello world");
        System.out.println(textBox_1.text.toUpperCase());

        }
    }

```

## Memory Allocation: 
In Java we have two main memories:
- Stack: is for storing objects, and primitive variables...
- Heap: is for storing objects.

When Creating an Object, the value is get stored in the heap while its addresse is stored in the Stack

**Example:**
In this example both variables textBox1 and textBox2 are having the same address, which mean they are pointing on the same location in the heap, so they have access to one instance

```java
    public static void main(String[] args) {
        var textBox1 = new TextBox();
        var textBox2 = textBox1;
        textBox1.setText("hello world");
        System.out.println(textBox1.text); // hello world
        System.out.println(textBox2.text); // hello world

        }

```

## 6- Procedural Programming: 

Procedural Programming means everything in the code is related, like write whole program in one file, without using oop or functional programming.

**Example:**
```java
public class Main {
    public static void main(String[] args) {
        int baseSalary = 50_000;
        int extraHours = 10;
        int hourlyRate = 20;

        int wage = calculateWage(baseSalary, extraHours, hourlyRate);
        System.out.println(wage);
        }
    public static int calculateWage(
            int baseSalary,
            int extraHours,
            int hourlyRate
    ){
        return baseSalary + (extraHours * hourlyRate);
    }
    }

```
## 7- Encapsulation:

*Encapsulation* means Bundle the data and methods that operate on the data in a single unit.   

**Example:**
In this example we will try to convert the example of 6th section to oop approach.
`Main.java`:
```java
package org.example;

public class Main {
    public static void main(String[] args) {
        var employee = new Employee();
        employee.baseSalary = 50_000;
        employee.hourlyRate = 20;
        int wage = employee.calculateWage(10);
        System.out.println(wage);
        }
    }

```

`Employee.java`:
```java
package org.example;

public class Employee {
    public int baseSalary;
    public int hourlyRate;

    public int calculateWage(int extraHours){
        return baseSalary + (hourlyRate * extraHours);
    }

}

```
## Getters and Setters:

Sometimes we have attributes that are sensitive, if their value doesn't meet some conditions, our program will crash, the solution is to make those attribues `private` and define get and set methods.

**Example:**
`Employee.java`:
```java
package org.example;

public class Employee {
    private int baseSalary;
    private int hourlyRate;

    public int calculateWage(int extraHours){
        return baseSalary + (hourlyRate * extraHours);
    }

    public void setBaseSalary(int baseSalary) {
        if (baseSalary < 0) {
            throw new IllegalArgumentException("Base Salary cannot be negative");
        }
        this.baseSalary = baseSalary;
    }
    public int getBaseSalary() {
        return baseSalary;
    }
    public void setHourlyRate(int hourlyRate) {
        if (hourlyRate < 0) {
            throw new IllegalArgumentException("Hourly Rate cannot be negative");
        }
        this.hourlyRate = hourlyRate;
    }
    public int getHourlyRate() {
        return hourlyRate;
    }
}

```
`Main.java`:
```java
package org.example;

public class Main {
    public static void main(String[] args) {
        var employee = new Employee();
        employee.setBaseSalary(50_000);
        employee.setHourlyRate(20);
        int wage = employee.calculateWage(10);
        System.out.println(wage);
        }
    }

```




