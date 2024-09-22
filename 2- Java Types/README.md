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

## Strings

**String** is a _reference type_

> Strings are immutable, when calling a method like replace, it doesn't update the value of the string, but create another refernece with new value

```java
package org.example;


//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        //using Date class
        String message = "Hello World" + "!!";
        System.out.println(message.endsWith("!!"));
        System.out.println(message.startsWith("!!"));
        System.out.println(message.indexOf("h"));
        System.out.println(message.replace("!!","**"));
        System.out.println(message.toLowerCase());
        System.out.println(message.trim()); // it removes spaces in the beginning and the end of the string
        }
    }

```

```Output
true
false
-1
Hello World**
hello world!!
Hello World!!

```

## Escape Sequences:

In Java there is some special characters we can't type them direclty in a string like " or \

```java
package org.example;


//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        //using Date class
        String message = "Hello \"world\" \nhello \t world \\";
        System.out.println(message);
        }
    }
```

```Output
Hello "world"
hello   world \
```

## Array

Array it's a reference type, it conains multiple values of the same type.

> Arrays in Java have fixed size, to get the size we use method length from _Arrays_ class.

**Syntaxe:**

```
type[] name = new type[size];
type[] name = {...values};
```

**Example:**

```java
package org.example;


import java.util.Arrays;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        //using Date class
        int[] numbers = new int[5];
        int[] odds = {1,3,5,7,9};
        numbers[0] = 4;
        numbers[3] = 8;
        System.out.println(Arrays.toString(odds));
        System.out.println(odds); // it prints the Reference id of the array
        System.out.println(Arrays.toString(numbers));
        System.out.println(numbers); // it prints the Reference id of the array
        }
    }

```

```Output
[1, 3, 5, 7, 9]
[I@341b80b2
[4, 0, 0, 8, 0]
[I@55a1c291
```

## Multi-dimensional arrays:

In last section we define a one dimensional array, but in facts we can have multi-dimensional array, like matrix, tensors etc...

**Example**:

```java
package org.example;


import java.util.Arrays;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        //using Date class
        int[][] numbers = new int[2][3];
        int [][] odds = {{1,2,5},{7,9,11}};

        numbers[1][0] = 1;
        numbers[1][1] = 2;
        numbers[1][2] = 3;

        odds[0][2] = 3;
        System.out.println(numbers);
        System.out.println(Arrays.toString(numbers)); // it convert just the array that contains those arrays
        System.out.println(Arrays.deepToString(numbers)); // we use this method to convert all nested arrays to string
        System.out.println(Arrays.deepToString(odds));

        }
    }

```

```Output
[[I@3b938003
[[I@6f3b5d16, [I@78b1cc93]
[[0, 0, 0], [1, 2, 3]]
[[1, 2, 3], [7, 9, 11]]
```

## Constants

Constants are variables that we can't change their value throught the program.

**Syntaxe:**

```java
final float PI = 3.14F;
```

## Arithmetic Operations:

Java has same arithmetic operations of many other programming language like C, C++, Python, JavaScript..., like(+,-,\*,/,%)

**Example:**

```java
package org.example;


import java.util.Arrays;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        int result = 10/3;
        double realResult = (double) 10/ (double) 3;
        double testResult = 10/3;

        System.out.println(result);
        System.out.println(realResult);
        System.out.println(testResult);
        int x = 1;
        x +=2;
        x++;
        ++x;
        int y = ++x;
        int z = x++;
        System.out.println("this about incrementing ");
        System.out.println(x);
        System.out.println(y);
        System.out.println(z);
        }
    }

```

**Output**

```
3
3.3333333333333335
3.0
this about incrementing
7
6
6

```

## Casting

There is two types of casting:

- Implicite Casting: while casting is done automatically
- Excplicite Casting: while casting is done in a manuall way

**Example**:

```java
package org.example;


import java.util.Arrays;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        //Implicit Casting
        short a = 3;
        int b = a + 2;
        //Explicit Casting
        double x = 1.1;
        String z = "1";
        String w = "1.1";
        int y = (int) x + 2;
        y = Integer.parseInt(z) + (int)Double.parseDouble(w);

        }
    }
```

## Math

Math in java is an object containing many useful methods like :

- round
- ceil
- floor
- min
- max
- random

<br>

**Example:**

```java
package org.example;


import java.util.Arrays;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        int x = Math.round(1.1F);
        System.out.println(x);
        double y = Math.floor(1.1);
        double z = Math.ceil(1.1);
        System.out.println(y);
        System.out.println(z);

        x = Math.max(1,5);
        System.out.println(x);
        //Playing with random

        double random = Math.random()*100;
        System.out.println(random);
        int randomInt = (int) (Math.random() * 100);
        System.out.println(randomInt);
        }
    }
```

**Output:**

```
1
1.0
2.0
5
70.98026632802153
38
```

## Formating Numbers:

Sometimes we need to format a number to a specific format, so in java we have a special class _NumberFormt_ which an abstract class, so we can't create a direct instance.

**Example:**

```java
package org.example;


import java.text.NumberFormat;
import java.util.Arrays;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
        NumberFormat currency = NumberFormat.getCurrencyInstance();
        String result = currency.format(1234321.3);
        System.out.println(result);

        result = NumberFormat.getPercentInstance().format(0.1); // here we introduced also method chaining
        System.out.println(result);

        }
    }

```

**Output:**

```
$1,234,321.30
10%
```
