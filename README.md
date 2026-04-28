# JavaFile
[Program-1 Wap for addition sub mul div using object and classes.](#ASSIGNMENT-1)

[Program-2 Write a class for addition of two distance where each distance is given in m, cm, mm.](#ASSIGNMENT-2)

[Program-3 Similarly, test the result by creation of object in main class where each distance is given in m, cm.](#ASSIGNMENT-3)

[Program-4 Similarly for time given in hours, minutes and seconds.](#ASSIGNMENT-4)

[Program-5 Time given in hours and minutes.](#ASSIGNMENT-5)

[Program-6 Collect code from internet for any five C programs (Factorial, Armstrong, Palindrome, Fibonacci, Pattern).](#ASSIGNMENT-6)

[Program-7 Write a class having four methods for 1D array (Input, Output1, Output2, Reverse).](#ASSIGNMENT-7)

[Program-8 Write a class with multiple methods for matrix operations (Transpose, Addition, Row sum, Column sum, Diagonal sum).](#ASSIGNMENT-8)

[Program-9 Multithreading: Print 1-100 using three classes (with & without thread) and using Runnable interface.](#ASSIGNMENT-9)

[Program-10 Synchronization using join method in multithreading.](#ASSIGNMENT-10)

[Program-11 Addition of two numbers using Swing.](#ASSIGNMENT-11)

[Program-12 Registration form with 10 elements and database connectivity using JDBC.](#ASSIGNMENT-12)

[Program-13 Calculator using Swing.](#ASSIGNMENT-13)

[Program-14 Matrix Addition using Swing.](#ASSIGNMENT-14)

[Program-15 JFrame with 10 buttons to draw shapes (circle, oval, rectangle, etc.).](#ASSIGNMENT-15)

[Program-16 Paint brush using Mouse Events with color and width selection.](#ASSIGNMENT-16)

[Program-17 Create a package with 5 classes and import it.](#ASSIGNMENT-17)

[Program-18 Create a package and subpackage, import and test it.](#ASSIGNMENT-18)

[Program-19 Array of size 5 with ArrayIndexOutOfBoundsException and ArithmeticException using try-catch.](#ASSIGNMENT-19)

[Program-20 User-defined exception to test age range of a student.](#ASSIGNMENT-20)

[Program-21 File handling programs.](#ASSIGNMENT-21)

[Program-22 Inheritance programs using interface and abstract class.](#ASSIGNMENT-22)

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

##ASSIGNMENT-4
```
public class Time {

    int hour;
    int minute;
    int second;

    // Constructor
    Time(int h, int m, int s) {
        hour = h;
        minute = m;
        second = s;
    }

    // Method to add two times
    Time addTime(Time t2) {
        int sec = this.second + t2.second;
        int min = this.minute + t2.minute;
        int hr  = this.hour + t2.hour;

        // convert seconds → minutes
        min += sec / 60;
        sec = sec % 60;

        // convert minutes → hours
        hr += min / 60;
        min = min % 60;

        return new Time(hr, min, sec);
    }

    // Display result
    void display() {
        System.out.println(hour + " hr " + minute + " min " + second + " sec");
    }

    // MAIN METHOD
    public static void main(String[] args) {

        Time t1 = new Time(2, 45, 50);
        Time t2 = new Time(3, 30, 20);

        Time result = t1.addTime(t2);

        System.out.print("Total Time = ");
        result.display();
    }
}
```
<img width="768" height="441" alt="image" src="https://github.com/user-attachments/assets/03cc79a0-918d-4a3d-a180-505790e259f6" />

##ASSIGNMENT-5
```
public class TimeHM {

    int hour;
    int minute;

    // Constructor
    TimeHM(int h, int m) {
        hour = h;
        minute = m;
    }

    // Method to add two times
    TimeHM addTime(TimeHM t2) {
        int min = this.minute + t2.minute;
        int hr  = this.hour + t2.hour;

        // convert minutes → hours
        hr += min / 60;
        min = min % 60;

        return new TimeHM(hr, min);
    }

    // Display result
    void display() {
        System.out.println(hour + " hr " + minute + " min");
    }

    // MAIN METHOD
    public static void main(String[] args) {

        TimeHM t1 = new TimeHM(2, 45);
        TimeHM t2 = new TimeHM(3, 30);

        TimeHM result = t1.addTime(t2);

        System.out.print("Total Time = ");
        result.display();
    }
}
```
<img width="852" height="371" alt="image" src="https://github.com/user-attachments/assets/8078d02f-59f9-4609-afe6-254a85d5f1c3" />

##ASSIGNMENT-6
```
public class BasicPrograms {

    // 1️⃣ Factorial
    static void factorial() {
        int n = 5;
        long fact = 1;

        for(int i = 1; i <= n; i++)
            fact *= i;

        System.out.println("Factorial of " + n + " = " + fact);
    }

    // 2️⃣ Armstrong Number
    static void armstrong() {
        int num = 153, original, remainder;
        int result = 0;

        original = num;

        while(original != 0) {
            remainder = original % 10;
            result += remainder * remainder * remainder;
            original /= 10;
        }

        if(result == num)
            System.out.println(num + " is Armstrong Number");
        else
            System.out.println(num + " is Not Armstrong Number");
    }

    // 3️⃣ Palindrome Number
    static void palindrome() {
        int num = 121, reversed = 0, remainder, original;
        original = num;

        while(num != 0) {
            remainder = num % 10;
            reversed = reversed * 10 + remainder;
            num /= 10;
        }

        if(original == reversed)
            System.out.println(num + " is Palindrome Number");
        else
            System.out.println(num + " is Not Palindrome");
    }

    // 4️⃣ Fibonacci Series
    static void fibonacci() {
        int n = 10;
        int a = 0, b = 1, c;

        System.out.print("Fibonacci Series: " + a + " " + b + " ");
        for(int i = 3; i <= n; i++) {
            c = a + b;
            System.out.print(c + " ");
            a = b;
            b = c;
        }
        System.out.println();
    }

    // 5️⃣ Star Pattern
    static void pattern() {
        int rows = 5;
        System.out.println("Star Pattern:");
        for(int i = 1; i <= rows; i++) {
            for(int j = 1; j <= rows - i; j++)
                System.out.print(" ");
            for(int j = 1; j <= (2*i - 1); j++)
                System.out.print("*");
            System.out.println();
        }
    }

    // MAIN METHOD
    public static void main(String[] args) {

        factorial();
        armstrong();
        palindrome();
        fibonacci();
        pattern();
    }
}
```
<img width="646" height="384" alt="image" src="https://github.com/user-attachments/assets/e3994e50-c8e1-454a-9f42-7f2646fce8e3" />

##ASSIGNMENT-7
```
import java.util.Scanner;

public class ArrayOperations {

    int arr[] = new int[100];
    int n;

    //  Input Method
    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of elements: ");
        n = sc.nextInt();

        System.out.println("Enter elements:");
        for(int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
    }

    //  Output Method 1 (using for loop)
    void output1() {
        System.out.println("Array elements (Method 1):");
        for(int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    //  Output Method 2 (using for-each loop)
    void output2() {
        System.out.println("Array elements (Method 2):");
        for(int x : arr) {
            if(x != 0)   // to avoid printing empty elements
                System.out.print(x + " ");
        }
        System.out.println();
    }

    //  Reverse Method
    void reverse() {
        System.out.println("Reversed Array:");
        for(int i = n - 1; i >= 0; i--) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    // MAIN METHOD
    public static void main(String[] args) {
        ArrayOperations obj = new ArrayOperations();

        obj.input();
        obj.output1();
        obj.output2();
        obj.reverse();
    }
}
```
<img width="467" height="392" alt="image" src="https://github.com/user-attachments/assets/d399192c-c877-4a42-bf05-376a73af2033" />

##ASSIGNMENT-8
```
import java.util.Scanner;

public class MatrixOperations {

    int r, c;
    int a[][] = new int[10][10];
    int b[][] = new int[10][10];

    // Input Matrix
    void inputMatrices() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter rows and columns: ");
        r = sc.nextInt();
        c = sc.nextInt();

        System.out.println("Enter Matrix A:");
        for(int i=0;i<r;i++)
            for(int j=0;j<c;j++)
                a[i][j] = sc.nextInt();

        System.out.println("Enter Matrix B:");
        for(int i=0;i<r;i++)
            for(int j=0;j<c;j++)
                b[i][j] = sc.nextInt();
    }

    // Matrix Addition
    void addition() {
        System.out.println("\nMatrix Addition:");
        for(int i=0;i<r;i++) {
            for(int j=0;j<c;j++) {
                System.out.print((a[i][j] + b[i][j]) + " ");
            }
            System.out.println();
        }
    }

    // Transpose of Matrix A
    void transpose() {
        System.out.println("\nTranspose of Matrix A:");
        for(int i=0;i<c;i++) {
            for(int j=0;j<r;j++) {
                System.out.print(a[j][i] + " ");
            }
            System.out.println();
        }
    }

    // Sum of Rows (Matrix A)
    void sumOfRows() {
        System.out.println("\nSum of Rows (Matrix A):");
        for(int i=0;i<r;i++) {
            int sum = 0;
            for(int j=0;j<c;j++)
                sum += a[i][j];
            System.out.println("Row " + (i+1) + " Sum = " + sum);
        }
    }

    // Sum of Columns (Matrix A)
    void sumOfColumns() {
        System.out.println("\nSum of Columns (Matrix A):");
        for(int i=0;i<c;i++) {
            int sum = 0;
            for(int j=0;j<r;j++)
                sum += a[j][i];
            System.out.println("Column " + (i+1) + " Sum = " + sum);
        }
    }

    // Sum of Diagonals (Matrix A)
    void sumOfDiagonals() {
        int primary = 0, secondary = 0;
        for(int i=0;i<r;i++) {
            primary += a[i][i];
            secondary += a[i][r-i-1];
        }
        System.out.println("\nPrimary Diagonal Sum = " + primary);
        System.out.println("Secondary Diagonal Sum = " + secondary);
    }

    // MAIN METHOD
    public static void main(String[] args) {
        MatrixOperations obj = new MatrixOperations();
        obj.inputMatrices();
        obj.addition();
        obj.transpose();
        obj.sumOfRows();
        obj.sumOfColumns();
        obj.sumOfDiagonals();
    }
}
```
<img width="605" height="381" alt="image" src="https://github.com/user-attachments/assets/f2a25e14-3dc2-4e00-bc57-ebf7f248fbc1" />

##ASSIGNMENT-9
```
// Class 1 – Without Thread (Normal execution)
class WithoutThread {
    void printNumbers() {
        for(int i = 1; i <= 100; i++)
            System.out.println("WithoutThread: " + i);
    }
}

// Class 2 – Thread 1
class MyThread1 extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++)
            System.out.println("Thread-1: " + i);
    }
}

// Class 3 – Thread 2
class MyThread2 extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++)
            System.out.println("Thread-2: " + i);
    }
}

public class ThreadDemo {
    public static void main(String[] args) {

        System.out.println("----- Without Thread -----");
        WithoutThread obj = new WithoutThread();
        obj.printNumbers();

        System.out.println("\n----- With Thread -----");
        MyThread1 t1 = new MyThread1();
        MyThread2 t2 = new MyThread2();

        t1.start();
        t2.start();
    }
}
```
<img width="735" height="409" alt="image" src="https://github.com/user-attachments/assets/1107930d-722c-4d46-8151-dac63a9387a9" />

##ASSIGNMENT-10
```
class Thread1 extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++)
            System.out.println("Thread-1: " + i);
    }
}

class Thread2 extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++)
            System.out.println("Thread-2: " + i);
    }
}

class Thread3 extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++)
            System.out.println("Thread-3: " + i);
    }
}

public class ThreadJoinDemo {
    public static void main(String[] args) {

        Thread1 t1 = new Thread1();
        Thread2 t2 = new Thread2();
        Thread3 t3 = new Thread3();

        try {
            // Start first thread
            t1.start();
            t1.join();   // wait until t1 finishes

            // Start second thread
            t2.start();
            t2.join();   // wait until t2 finishes

            // Start third thread
            t3.start();
            t3.join();   // wait until t3 finishes

        } catch(InterruptedException e) {
            System.out.println(e);
        }
    }
}
```
<img width="601" height="371" alt="image" src="https://github.com/user-attachments/assets/7796468b-524e-4df5-9787-a5e3a3b0e7be" />

##ASSIGNMENT-11
```
import javax.swing.*;
import java.awt.event.*;

public class AdditionSwing extends JFrame implements ActionListener {

    JTextField t1, t2, t3;
    JButton btn;

    AdditionSwing() {
        // Labels
        JLabel l1 = new JLabel("Enter First Number:");
        l1.setBounds(30, 30, 150, 30);
        add(l1);

        JLabel l2 = new JLabel("Enter Second Number:");
        l2.setBounds(30, 70, 150, 30);
        add(l2);

        JLabel l3 = new JLabel("Result:");
        l3.setBounds(30, 110, 150, 30);
        add(l3);

        // Text fields
        t1 = new JTextField();
        t1.setBounds(180, 30, 150, 30);
        add(t1);

        t2 = new JTextField();
        t2.setBounds(180, 70, 150, 30);
        add(t2);

        t3 = new JTextField();
        t3.setBounds(180, 110, 150, 30);
        t3.setEditable(false);
        add(t3);

        // Button
        btn = new JButton("Add");
        btn.setBounds(120, 160, 100, 30);
        btn.addActionListener(this);
        add(btn);

        // Frame settings
        setTitle("Addition using Swing");
        setSize(400, 300);
        setLayout(null);
        setVisible(true);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }

    // Button click event
    public void actionPerformed(ActionEvent e) {
        int a = Integer.parseInt(t1.getText());
        int b = Integer.parseInt(t2.getText());
        int sum = a + b;
        t3.setText(String.valueOf(sum));
    }

    // Main method
    public static void main(String[] args) {
        new AdditionSwing();
    }
}
```
<img width="857" height="387" alt="image" src="https://github.com/user-attachments/assets/c27f7fec-8370-4cce-bcb0-126e1c9c4cb5" />

##ASSIGNMENT-12
```
import javax.swing.*;
import java.awt.event.*;
import java.sql.*;

public class RegistrationForm extends JFrame implements ActionListener {

    JTextField t1,t2,t6,t7,t8,t9,t10;
    JPasswordField t3;
    JRadioButton r1,r2;
    JComboBox c1;
    JTextArea ta;
    JButton btn;

    RegistrationForm() {

        setTitle("Student Registration Form");
        setSize(500,600);
        setLayout(null);

        JLabel l1=new JLabel("Name"); l1.setBounds(50,30,100,30); add(l1);
        t1=new JTextField(); t1.setBounds(200,30,200,30); add(t1);

        JLabel l2=new JLabel("Email"); l2.setBounds(50,70,100,30); add(l2);
        t2=new JTextField(); t2.setBounds(200,70,200,30); add(t2);

        JLabel l3=new JLabel("Password"); l3.setBounds(50,110,100,30); add(l3);
        t3=new JPasswordField(); t3.setBounds(200,110,200,30); add(t3);

        JLabel l4=new JLabel("Gender"); l4.setBounds(50,150,100,30); add(l4);
        r1=new JRadioButton("Male"); r2=new JRadioButton("Female");
        r1.setBounds(200,150,80,30); r2.setBounds(280,150,100,30);
        ButtonGroup bg=new ButtonGroup(); bg.add(r1); bg.add(r2);
        add(r1); add(r2);

        JLabel l5=new JLabel("Course"); l5.setBounds(50,190,100,30); add(l5);
        String course[]={"BCA","B.Tech","BBA","MCA"};
        c1=new JComboBox(course);
        c1.setBounds(200,190,200,30); add(c1);

        JLabel l6=new JLabel("Phone"); l6.setBounds(50,230,100,30); add(l6);
        t6=new JTextField(); t6.setBounds(200,230,200,30); add(t6);

        JLabel l7=new JLabel("Address"); l7.setBounds(50,270,100,30); add(l7);
        ta=new JTextArea(); ta.setBounds(200,270,200,60); add(ta);

        JLabel l8=new JLabel("City"); l8.setBounds(50,340,100,30); add(l8);
        t7=new JTextField(); t7.setBounds(200,340,200,30); add(t7);

        JLabel l9=new JLabel("State"); l9.setBounds(50,380,100,30); add(l9);
        t8=new JTextField(); t8.setBounds(200,380,200,30); add(t8);

        JLabel l10=new JLabel("Pincode"); l10.setBounds(50,420,100,30); add(l10);
        t9=new JTextField(); t9.setBounds(200,420,200,30); add(t9);

        btn=new JButton("Register");
        btn.setBounds(180,470,120,40);
        btn.addActionListener(this);
        add(btn);

        setVisible(true);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent e) {
        try {
            String name=t1.getText();
            String email=t2.getText();
            String pass=new String(t3.getPassword());
            String gender=r1.isSelected()?"Male":"Female";
            String course=(String)c1.getSelectedItem();
            String phone=t6.getText();
            String address=ta.getText();
            String city=t7.getText();
            String state=t8.getText();
            String pin=t9.getText();

            // JDBC Connection
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con=DriverManager.getConnection(
              "jdbc:mysql://localhost:3306/studentdb","root","");

            String sql="insert into registration(name,email,password,gender,course,phone,address,city,state,pincode) values(?,?,?,?,?,?,?,?,?,?)";
            PreparedStatement ps=con.prepareStatement(sql);

            ps.setString(1,name);
            ps.setString(2,email);
            ps.setString(3,pass);
            ps.setString(4,gender);
            ps.setString(5,course);
            ps.setString(6,phone);
            ps.setString(7,address);
            ps.setString(8,city);
            ps.setString(9,state);
            ps.setString(10,pin);

            ps.executeUpdate();
            JOptionPane.showMessageDialog(this,"Registration Successful!");

            con.close();

        } catch(Exception ex) {
            JOptionPane.showMessageDialog(this,ex);
        }
    }

    public static void main(String[] args) {
        new RegistrationForm();
    }
}
```
##ASSIGNMENT-13
```
import javax.swing.*;
import java.awt.event.*;

public class CalculatorSwing extends JFrame implements ActionListener {

    JTextField t1, t2, t3;
    JButton add, sub, mul, div;

    CalculatorSwing() {
        setTitle("Simple Calculator");
        setSize(400,300);
        setLayout(null);

        JLabel l1 = new JLabel("First Number:");
        l1.setBounds(30,30,120,30);
        add(l1);

        JLabel l2 = new JLabel("Second Number:");
        l2.setBounds(30,70,120,30);
        add(l2);

        JLabel l3 = new JLabel("Result:");
        l3.setBounds(30,110,120,30);
        add(l3);

        t1 = new JTextField();
        t1.setBounds(160,30,150,30);
        add(t1);

        t2 = new JTextField();
        t2.setBounds(160,70,150,30);
        add(t2);

        t3 = new JTextField();
        t3.setBounds(160,110,150,30);
        t3.setEditable(false);
        add(t3);

        add = new JButton("+");
        sub = new JButton("-");
        mul = new JButton("*");
        div = new JButton("/");

        add.setBounds(30,170,70,40);
        sub.setBounds(110,170,70,40);
        mul.setBounds(190,170,70,40);
        div.setBounds(270,170,70,40);

        add(add); add(sub); add(mul); add(div);

        add.addActionListener(this);
        sub.addActionListener(this);
        mul.addActionListener(this);
        div.addActionListener(this);

        setVisible(true);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent e) {
        double a = Double.parseDouble(t1.getText());
        double b = Double.parseDouble(t2.getText());
        double result = 0;

        if(e.getSource() == add)
            result = a + b;
        else if(e.getSource() == sub)
            result = a - b;
        else if(e.getSource() == mul)
            result = a * b;
        else if(e.getSource() == div)
            result = a / b;

        t3.setText(String.valueOf(result));
    }

    public static void main(String[] args) {
        new CalculatorSwing();
    }
}
```
<img width="482" height="368" alt="image" src="https://github.com/user-attachments/assets/488646bd-9057-49e8-bf64-0ed889d1512a" />

##ASSIGNMENT-14
```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class MatrixAdditionSwing extends JFrame implements ActionListener {

    JTextField a11,a12,a21,a22;
    JTextField b11,b12,b21,b22;
    JTextField r11,r12,r21,r22;
    JButton addBtn;

    MatrixAdditionSwing() {
        setTitle("Matrix Addition");
        setSize(400,350);
        setLayout(new GridLayout(6,4,5,5));
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Matrix A
        add(new JLabel("Matrix A"));
        add(new JLabel(""));
        add(new JLabel("Matrix B"));
        add(new JLabel(""));

        a11=new JTextField(); a12=new JTextField();
        b11=new JTextField(); b12=new JTextField();
        a21=new JTextField(); a22=new JTextField();
        b21=new JTextField(); b22=new JTextField();

        add(a11); add(a12); add(b11); add(b12);
        add(a21); add(a22); add(b21); add(b22);

        // Button
        addBtn = new JButton("Add Matrices");
        addBtn.addActionListener(this);
        add(addBtn);

        add(new JLabel("Result"));
        add(new JLabel(""));
        add(new JLabel(""));

        // Result fields
        r11=new JTextField(); r12=new JTextField();
        r21=new JTextField(); r22=new JTextField();

        r11.setEditable(false); r12.setEditable(false);
        r21.setEditable(false); r22.setEditable(false);

        add(r11); add(r12); add(r21); add(r22);

        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        int A11=Integer.parseInt(a11.getText());
        int A12=Integer.parseInt(a12.getText());
        int A21=Integer.parseInt(a21.getText());
        int A22=Integer.parseInt(a22.getText());

        int B11=Integer.parseInt(b11.getText());
        int B12=Integer.parseInt(b12.getText());
        int B21=Integer.parseInt(b21.getText());
        int B22=Integer.parseInt(b22.getText());

        r11.setText(String.valueOf(A11+B11));
        r12.setText(String.valueOf(A12+B12));
        r21.setText(String.valueOf(A21+B21));
        r22.setText(String.valueOf(A22+B22));
    }

    public static void main(String[] args) {
        new MatrixAdditionSwing();
    }
}
```
<img width="535" height="435" alt="image" src="https://github.com/user-attachments/assets/225533ae-1872-47ae-82f5-d3c9592d14be" />
##ASSIGNMENT-15
```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class MatrixAdditionSwing extends JFrame implements ActionListener {

    JTextField a11,a12,a21,a22;
    JTextField b11,b12,b21,b22;
    JTextField r11,r12,r21,r22;
    JButton addBtn;

    MatrixAdditionSwing() {
        setTitle("Matrix Addition");
        setSize(400,350);
        setLayout(new GridLayout(6,4,5,5));
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Matrix A
        add(new JLabel("Matrix A"));
        add(new JLabel(""));
        add(new JLabel("Matrix B"));
        add(new JLabel(""));

        a11=new JTextField(); a12=new JTextField();
        b11=new JTextField(); b12=new JTextField();
        a21=new JTextField(); a22=new JTextField();
        b21=new JTextField(); b22=new JTextField();

        add(a11); add(a12); add(b11); add(b12);
        add(a21); add(a22); add(b21); add(b22);

        // Button
        addBtn = new JButton("Add Matrices");
        addBtn.addActionListener(this);
        add(addBtn);

        add(new JLabel("Result"));
        add(new JLabel(""));
        add(new JLabel(""));

        // Result fields
        r11=new JTextField(); r12=new JTextField();
        r21=new JTextField(); r22=new JTextField();

        r11.setEditable(false); r12.setEditable(false);
        r21.setEditable(false); r22.setEditable(false);

        add(r11); add(r12); add(r21); add(r22);

        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        int A11=Integer.parseInt(a11.getText());
        int A12=Integer.parseInt(a12.getText());
        int A21=Integer.parseInt(a21.getText());
        int A22=Integer.parseInt(a22.getText());

        int B11=Integer.parseInt(b11.getText());
        int B12=Integer.parseInt(b12.getText());
        int B21=Integer.parseInt(b21.getText());
        int B22=Integer.parseInt(b22.getText());

        r11.setText(String.valueOf(A11+B11));
        r12.setText(String.valueOf(A12+B12));
        r21.setText(String.valueOf(A21+B21));
        r22.setText(String.valueOf(A22+B22));
    }

    public static void main(String[] args) {
        new MatrixAdditionSwing();
    }
}

```
<img width="979" height="700" alt="image" src="https://github.com/user-attachments/assets/d566fabb-6720-4356-8d32-eb90b9f0f9da" />
##ASSIGNMENT-17
```
import mypack.*;   // importing the package

public class MainApp {

    public static void main(String[] args) {

        Addition a = new Addition();
        Subtraction s = new Subtraction();
        Multiplication m = new Multiplication();
        Division d = new Division();
        Greeting g = new Greeting();

        System.out.println("Addition = " + a.add(10,5));
        System.out.println("Subtraction = " + s.sub(10,5));
        System.out.println("Multiplication = " + m.mul(10,5));
        System.out.println("Division = " + d.div(10,5));
        
        g.sayHello();
    }
}
```
<img width="777" height="395" alt="image" src="https://github.com/user-attachments/assets/24d0d871-e7a2-4fe1-a001-3554bbf54dc4" />

##ASSIGNMENT-18
```
public class MainApp {

    public static void main(String[] args) {

        Addition a = new Addition();
        Subtraction s = new Subtraction();

        System.out.println("Addition: " + a.add(10, 5));
        System.out.println("Subtraction: " + s.subtract(10, 5));
    }
}

class Addition {
    int add(int a, int b) {
        return a + b;
    }
}

class Subtraction {
    int subtract(int a, int b) {
        return a - b;
    }
}
```
<img width="833" height="386" alt="image" src="https://github.com/user-attachments/assets/997e2807-09ab-4334-a3b1-766566df3fea" />

##ASSIGNMENT-19
```
public class ExceptionDemo {

    public static void main(String[] args) {

        // -------- ARRAY EXCEPTION --------
        int[] arr = new int[5];

        try {
            System.out.println("Accessing array elements...");

            for (int i = 0; i <= 5; i++) { // intentionally wrong (0–5)
                arr[i] = i * 10;
                System.out.println("arr[" + i + "] = " + arr[i]);
            }

        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Error: You tried to access an index outside the array size!");
            System.out.println("Details: " + e);
        }

        System.out.println("\n-----------------------------\n");

        // -------- ARITHMETIC EXCEPTION --------
        try {
            System.out.println("Performing division...");

            int a = 10;
            int b = 0; // will cause exception

            int result = a / b;

            System.out.println("Result: " + result);

        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero is not allowed!");
            System.out.println("Details: " + e);
        }

        System.out.println("\nProgram continues after handling exceptions.");
    }
}
```
<img width="653" height="471" alt="image" src="https://github.com/user-attachments/assets/d7f41f4f-acd1-417e-a346-95f7c9b2abd9" />

##ASSIGNMENT-20
```
// User-defined exception
class InvalidAgeException extends Exception {

    public InvalidAgeException(String message) {
        super(message);
    }
}

public class AgeTest {

    // Method to check age
    static void checkAge(int age) throws InvalidAgeException {

        if (age < 18 || age > 25) {
            throw new InvalidAgeException("Invalid age! Age must be between 18 and 25.");
        } else {
            System.out.println("Valid age. Student accepted.");
        }
    }

    public static void main(String[] args) {

        int age = 30; // change this value to test

        try {
            checkAge(age);
        } catch (InvalidAgeException e) {
            System.out.println("Exception caught: " + e.getMessage());
        }
    }
}
```
<img width="724" height="390" alt="image" src="https://github.com/user-attachments/assets/c3316a63-a62f-46cc-93f6-beed757eae89" />
##ASSIGNMENT-21
```
// -------- INTERFACE --------
interface Shape {
    void draw();
}

// -------- ABSTRACT CLASS --------
abstract class Vehicle {
    abstract void start();

    void fuel() {
        System.out.println("Vehicle uses fuel");
    }
}

// -------- INHERITANCE --------
class Animal {
    void eat() {
        System.out.println("Animal eats food");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

// -------- CLASS USING INTERFACE --------
class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

// -------- CLASS USING ABSTRACT CLASS --------
class Car extends Vehicle {
    void start() {
        System.out.println("Car starts with key");
    }
}

// -------- MAIN CLASS --------
public class AllInOneDemo {

    public static void main(String[] args) {

        // Inheritance
        Dog d = new Dog();
        d.eat();
        d.bark();

        System.out.println("------------------");

        // Interface
        Shape s = new Circle();
        s.draw();

        System.out.println("------------------");

        // Abstract Class
        Car c = new Car();
        c.start();
        c.fuel();
    }
}
```
<img width="541" height="381" alt="image" src="https://github.com/user-attachments/assets/14d24ed1-2f6a-4f3f-8ba2-a09b3647f782" />
