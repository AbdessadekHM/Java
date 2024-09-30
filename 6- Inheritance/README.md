# Inheritance

## Definition

in Java by which one class is allowed to inherit the features(fields and methods) of another class. In Java, Inheritance means creating new classes based on existing ones. A class that inherits from another class can reuse the methods and fields of that class. In addition, you can add new fields and methods to your current class as well.

**Syntaxe:**

```java
public class Child extends Parent{

}
//The Child class will inherite methods and attributes that are public or protected in Parent Class
```

## The Object Class

the `object` class is a special class in java, and it's the parent of all existance classes.

**Example:**

```java
var object = new Object();
```

and all classes in java inherite from object class, and there is some special method in that class: <br>

```java
var employee = new Employee();
var employee1 = new Employee();
employee.toString() // give the full class name com.domain.className@hashedAddressInHexadecimal
employee.hashCode() // return the hash of the code in decimal
employee.equal(employee1); // it compare the address code so the result of that statement is 'false'
```

## Constructor And Inheritance:

**Example:**<br>
`UiControl.java`: <br>

```java
package org.example;

public class UiControl {
    private boolean isEnabled = true;

    public UiControl(boolean isEnabled) {
       this.isEnabled = isEnabled;
        System.out.println("UiControl");
    }
    public void enable(){
        isEnabled = true;
    }
    public void disable(){
        isEnabled = false;
    }
    public boolean isEnabled(){
        return isEnabled;
    }
}

```

`TextBox.java`:

```java
package org.example;

public class TextBox extends UiControl {
  public String text = "";

  public TextBox(boolean isEnabled) {
    super(isEnabled);
    System.out.println("textBox");
  }
  public void setText(String text) {
    this.text = text;
  }

  public void clear() {
    text = "";
  }
}
```

`Main.java`:

```java
package org.example;

public class Main {

    public static void main(String[] args) {
        var textBox = new TextBox(true);

    }
}
```

**Output:**

```
UiControl
Textbox
```

## Access Modifers:

In java we have 4 type of access modifiers:
**private**:
it's accessible just in inside of the class
**public**:
it's accessible from any place in the porject
**protected**:
it's accessible from any class exist in same package and child classes from any package
**default**
when letting the field without specifying the access modifier, the `default` is that field is accessible from any class in the same package and it's not from other packages even child classes.

## Overriding Methods:

to override a method we should add `@Override` anotation like the example below:

**Example:**

```java
  @Override
  public String toString(){
    return text;
  }
```

## Upcasting and Downcasting:

- upcasting: means to cast a child to a parent like casting textBox class to its parent UiControl, or any other class to the object class
- downcasting: means to cast a parent to a child, like the example below:

**Example:**

```java
package org.example;

public class Main {

    public static void main(String[] args) {
        var control = new UiControl(true);
        var textBox = new TextBox(true);
        show(textBox);

    }
    public static void show(UiControl control){
        if(control instanceof TextBox ){
            var textBox = (TextBox) control;
            textBox.setText("hello from overrided method");

        }
        System.out.println(control);
    }
}

```

## Equal && hashCode Overriding:

`Point.java`:

```java
package org.example;

import java.util.Objects;

public class Point {
    private int x;
    private int y;

    Point(int x, int y){
        this.x = x;
        this.y = y;
    }

    @Override
    public boolean equals(Object obj){
        if(this == obj) return true;
        if(!(obj instanceof Point)) return false;
        var other = (Point) obj;
        return x == other.x && y == other.y;

    }
    @Override
    public int hashCode(){
        return Objects.hash(x, y);
    }
}
```

`Main.java`:

```java
package org.example;

public class Main {

    public static void main(String[] args) {
        var point1 = new Point(1, 2);
        var point2 = new Point(1, 2);

        System.out.println(point1.equals(point2));
        System.out.println(point1==point2); // how??
        System.out.println(point1.hashCode());
        System.out.println(point2.hashCode());
    }
}

```

**Output**:

```
true
false
994
994
```

## Polymorhism:

a **Polymorhism** means many forms, imagine the scenario where we have the UiControl class having two children classes TextBox and CheckBox, if we have an array of UiControl and we want to render them we should control it depending on instances, with polymorphism we skip that problem by defining the method in the parent class, and overrid it in childs classes.

**Example:**

```java
public class UiControl {
  public void render(){

  }
}
public class TextBox extends UiControl {
  @Override
  public void render(){
    System.print.out("TextBox");
  }
}
public class CheckBox extends UiControl {
  @Override
  public void render(){
    System.print.out("CheckBox");
  }
}
```

## Abstract Classes and Methods:

abstract classes are classes that have at leasat one abstract method, with abstract classes we can't create instances.
for abstract methods, it's obligatory to override it in child classes

**Syntaxe:**

```java
public abstract class UiControl{
  public abstract render();

}
```

## Final Classes and Methods:

final classes are classes that can't be inherited, and final methods are methods that we can't override.

**Syntaxe:**

```java
public final class UiControl{
  public final render(){
    //Instructions
  }
}
```
