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
| boolean | 1     | true/false |

> For numbers, we may meet some issues in the type like shown in this example

```java
package org.example;

public class Main {
    public static void main(String[] args) {
            byte age = 30;
            float number = 10.99F;
            long counts = 3_000_000_000L;
        }
    }

```

## Reference Types

We use the Reference Types to store complex data like dates, mail message

**Example**

```java
package org.example;

import java.util.Date;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        //using Date class
            Date now = new Date();
            System.out.println(now);
        }
    }

```
