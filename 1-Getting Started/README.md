# Getting Started

## Table Of Content

- [Anatomy of Java](#anatomy-of-java)
- [How Java Code Gets Executed](#how-java-code-gets-executed)

## Anatomy of Java

Every java is build from blocks of functions contained by a class that must have the same name of the file, we call those functions by methods, a `method` is a function exists inside a class.
For the main class it should have the same name of the file as mentioned before, and have also a `main` method which is the entry point of our program

| As Convention we use in class naming Pascal Case, and Camel Case for methods <br>

Example of **Main.java**
<br>

```java
public class Main{
    public void main(String[] args) {

    }
}
```

## How Java Code Gets Executed

![Image_1](../assets/1.png)

> Like shown in the image 1, the compiler is the java kit we've installed to our machine

![Image_2](../assets/2.png)

> Java programs are plateforms independt, which mean it can be run in any plateforce, thanks to java virtual envinronement

**Summary** :
after compiling a java program we get a class file that can be running on any plateform.

anotehr thing mentioned in this sections, is packages, a `package` is a container for related classes, we orgiznie classes into packages

> As convention, in java the base package should be your domain in reverse
