# Interface: 

## What are Interfaces: 

We use Interfaces to build loosely-coupled, extensible, testable applications.

- Interface : What should be done
- class: how it should be done
  
**Syntaxe:**
```java
public interface Name{
    void  method1();
    int method2();
}
```

## Create an Interface:

> in some language like c# we have the convention to add I as prefix of interfaces, or add able at the end of the interface's name

**Example:**
`TaxCalculator`:
```java
package org.example;

public interface TaxCalculator {
    public double calculateTax();
}

```
`TaxCalculator2018`:
```java
package org.example;

public class TaxCalculator2018 implements TaxCalculator {
    private double amount;
    public TaxCalculator2018(double amount) {
        this.amount = amount;
    }

    @Override
    /*we used override here to make sure that this method it does exist in the interface and we override it,
     so in case the method is removed from the interface, an error is gonna be thrown. 
    */
    public double calculateTax(){

        return amount * 0.3;
    }
}
```
`TaxReport`:
```java
package org.example;

public class TaxReport {
    private TaxCalculator2018 calculator;

    public TaxReport() {
       calculator = new TaxCalculator2018(100_000);

    }
    public void show(){
        var tax = calculator.calculateTax();
        System.out.println(tax);
    }

}
```

## Dependency Injection:

<!-- this definitions is copied from digital ocean -->
**`Java Dependency`** Injection design pattern allows us to remove the hard-coded dependencies and make our application loosely coupled, extendable and maintainable. We can implement dependency injection in java to move the dependency resolution from compile-time to runtime. 

we will see 3 approaches of injection using same example of taxes from last sectoin.

### Constructor Injection 
`TaxReport`:

```java
package org.example;

public class TaxReport {
    private TaxCalculator calculator;

    public TaxReport(TaxCalculator calculator) {
        this.calculator = calculator;
    }
    public void show(){
        var tax = calculator.calculateTax();
        System.out.println(tax);
    }

}
```

`Main`:

```java
package org.example;

public class Main {

    public static void main(String[] args) {
        var taxCalculator = new TaxCalculator2018(100_000);
        var taxReport = new TaxReport(taxCalculator);
        taxReport.show();
    }
}
```
The Inconvenient of this approach, is when we have a lot of classes, it's applicable to create many instances in the main function.

### Setter Injection
it allows us to change the class dependency in the runtime.

In this example we add new class `TaxCalculator2019` and a set method inside the `TaxReport` class.

`TaxCalculator2019`:

```java
package org.example;

public class TaxCalculator2019 implements TaxCalculator {
    private double amount;

    public  TaxCalculator2019(double amount) {
       this.amount = amount;
    }
   public double calculateTax() {
       return 0;
   }
}
```

`TaxReport`:

```java
//same as this previous example 
public void setCalculator(TaxCalculator calculator){
    this.calculator = calculator;
}
```

`Main`:
```java
//same as the previous example
report.setCalculator(new TaxCalculator2019(50_000));
report.show();
```

### Method Injection:
In this approach we passe the dependency directly to methods.

`TaxReport`:

```java
package org.example;

public class TaxReport {

    public void show(TaxCalculator calculator){
        var tax = calculator.calculateTax();
        System.out.println(tax);
    }

}
```

`Main`:

```java
package org.example;

public class Main {

    public static void main(String[] args) {
        var taxCalculator = new TaxCalculator2018(100_000);
        var taxReport = new TaxReport();
        taxReport.show(taxCalculator);
        taxReport.show(new TaxCalculator2019(50_000));
    }
}
```
> the most used approach is constructor injection.
----------
