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
