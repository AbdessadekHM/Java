# Java Types

## Table of Content

## Variables:

**Variables** is a named storage location that holds a value or data(definition fro geeksforgeeks)

Syntaxe:

```
type identifier = value;
```

Example:

```java
package org.example;

public class Main {
    public static void main(String[] args) {
            int age = 30, temperature = 15;
            age = 35;
            int myAge = 20;
            int hisAge = myAge;
            System.out.println(age);
            System.out.println(hisAge);
        }
    }

```

## Primitve Types:

In Java we have two main types :

- Primitive Types: is for storing simple data such numbers characters booleans.
- Reference Types: for complex data like arrays objects etc...

Primitive Types are :

| Type    | Bytes | Range      |
| ------- | ----- | ---------- |
| byte    | 1     | [-128,127] |
| short   | 2     | [-32k,32k] |
| int     | 4     | [-2B,2B]   |
| long    | 8     |            |
| float   | 4     |            |
| double  | 8     |            |
| char    | 2     |            |
| boolean | 1     |            |
