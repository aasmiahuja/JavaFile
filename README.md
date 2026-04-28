# JavaFile
[Program-1 Wap for addition sub mul div using object and classes.](#ASSIGNMENT-1)
## ASSIGNMENT-1
```
package myproject;

import java.util.Scanner;

// Calculator class
class Calculator {
    double a, b;

    void getValues() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first number: ");
        a = sc.nextDouble();
        System.out.print("Enter second number: ");
        b = sc.nextDouble();
    }

    void add() {
        System.out.println("Addition = " + (a + b));
    }

    void subtract() {
        System.out.println("Subtraction = " + (a - b));
    }

    void multiply() {
        System.out.println("Multiplication = " + (a * b));
    }

    void divide() {
        if (b != 0)
            System.out.println("Division = " + (a / b));
        else
            System.out.println("Cannot divide by zero");
    }
}

// Main class (already created by NetBeans)
public class MyProject {

    public static void main(String[] args) {

        Calculator obj = new Calculator();  // object creation
        obj.getValues();

        obj.add();
        obj.subtract();
        obj.multiply();
        obj.divide();
    }
}
```
<img width="512" height="325" alt="image" src="https://github.com/user-attachments/assets/21314255-94c2-4ad1-8fb2-a8cf0be7a48f" />

## ASSIGNMENT-2
```
public class Distance {

    int meter;
    int centimeter;
    int millimeter;

    // Constructor
    Distance(int m, int cm, int mm) {
        meter = m;
        centimeter = cm;
        millimeter = mm;
    }

    // Method to add two distances
    Distance addDistance(Distance d2) {
        int mm = this.millimeter + d2.millimeter;
        int cm = this.centimeter + d2.centimeter;
        int m  = this.meter + d2.meter;

        // convert millimeter → centimeter
        cm += mm / 10;
        mm = mm % 10;

        // convert centimeter → meter
        m += cm / 100;
        cm = cm % 100;

        return new Distance(m, cm, mm);
    }

    // Display method
    void display() {
        System.out.println(meter + " m " + centimeter + " cm " + millimeter + " mm");
    }

    // MAIN METHOD (Program starts here)
    public static void main(String[] args) {

        Distance d1 = new Distance(5, 80, 9);
        Distance d2 = new Distance(3, 95, 8);

        Distance result = d1.addDistance(d2);

        System.out.print("Total Distance = ");
        result.display();
    }
}
```
<img width="516" height="225" alt="image" src="https://github.com/user-attachments/assets/f80e8d18-1e2e-472e-80b5-271c106dca15" />

## Assignment-3
```
public class Distance {

    int meter;
    int centimeter;
    int millimeter;

    // Constructor for meter + centimeter only
    Distance(int m, int cm) {
        meter = m;
        centimeter = cm;
        millimeter = 0;   // no mm given
    }

    // Method to add two distances
    Distance addDistance(Distance d2) {
        int cm = this.centimeter + d2.centimeter;
        int m  = this.meter + d2.meter;

        // convert cm → m
        m += cm / 100;
        cm = cm % 100;

        return new Distance(m, cm);
    }

    void display() {
        System.out.println(meter + " m " + centimeter + " cm");
    }

    // MAIN METHOD
    public static void main(String[] args) {

        // Distances given in meter and centimeter
        Distance d1 = new Distance(5, 80);
        Distance d2 = new Distance(3, 95);

        Distance result = d1.addDistance(d2);

        System.out.print("Total Distance = ");
        result.display();
    }
}
```
<img width="792" height="382" alt="image" src="https://github.com/user-attachments/assets/88105303-df09-444b-9c45-f509fb8b8382" />


