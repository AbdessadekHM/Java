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
