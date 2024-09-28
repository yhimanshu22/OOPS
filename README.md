# What is a Class?

A **class** in programming, specifically in object-oriented programming (OOP), is a blueprint or template that defines the structure and behavior of objects. It groups **data** (attributes or fields) and **methods** (functions) that work on the data into a single unit.

## Key Points:
1. **Blueprint for Objects**: A class is not an object itself, but it provides the structure from which objects (instances) are created.
2. **Attributes (Fields)**: These are variables defined within a class that store the properties or data of an object.
3. **Methods (Functions)**: These are the operations or behaviors that objects of the class can perform.

## Example of a Class in Java:

```java
// Defining a class named 'Car'
class Car {
    // Attributes (fields)
    String make;
    String model;
    int year;

    // Constructor (to initialize the object)
    Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Method (behavior) to display car details
    void displayDetails() {
        System.out.println("Car: " + make + " " + model + ", Year: " + year);
    }
}

// Using the class to create an object (instance)
public class Main {
    public static void main(String[] args) {
        // Creating an object of the Car class
        Car myCar = new Car("Toyota", "Camry", 2021);
        
        // Calling a method on the object
        myCar.displayDetails();  // Output: Car: Toyota Camry, Year: 2021
    }
}
```
---
# What is an Object?

An **object** is an instance of a class in object-oriented programming (OOP). It is a self-contained unit that consists of both **data** (attributes) and **methods** (functions or procedures) that operate on that data. Objects are the basic building blocks of OOP, allowing developers to model real-world entities in their code.

## Key Points:
1. **Instance of a Class**: An object is created based on a class definition, inheriting the structure and behavior defined in the class.
2. **State and Behavior**: Each object has its own state (represented by attributes) and behavior (represented by methods).
3. **Identity**: Every object has a unique identity, even if two objects have the same state.

## Example of an Object in Java:

```java
// Defining a class named 'Car'
class Car {
    // Attributes (fields)
    String make;
    String model;
    int year;

    // Constructor (to initialize the object)
    Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Method (behavior) to display car details
    void displayDetails() {
        System.out.println("Car: " + make + " " + model + ", Year: " + year);
    }
}

// Using the class to create objects (instances)
public class Main {
    public static void main(String[] args) {
        // Creating objects of the Car class
        Car myCar = new Car("Toyota", "Camry", 2021);
        Car anotherCar = new Car("Honda", "Accord", 2020);
        
        // Calling methods on the objects
        myCar.displayDetails();     // Output: Car: Toyota Camry, Year: 2021
        anotherCar.displayDetails(); // Output: Car: Honda Accord, Year: 2020
    }
}
```
---
# What is Encapsulation?

**Encapsulation** is a fundamental concept in object-oriented programming (OOP) that refers to the bundling of data (attributes) and methods (functions) that operate on that data into a single unit, known as a class. It restricts direct access to some of the object's components and can prevent the accidental modification of data. The primary goal of encapsulation is to protect the integrity of the data and ensure that it is only manipulated through well-defined interfaces.

## Key Points:
1. **Data Hiding**: Encapsulation allows the internal state of an object to be hidden from the outside world. Only the methods defined in the class can access and modify the internal data.
2. **Controlled Access**: By using access modifiers (such as private, protected, and public), encapsulation controls how the data is accessed and modified.
3. **Increased Security**: By restricting access to certain data, encapsulation enhances the security of the application.

## Example of Encapsulation in Java:

```java
// Defining a class named 'BankAccount'
class BankAccount {
    // Private attributes (state)
    private String accountNumber;
    private double balance;

    // Constructor to initialize the account
    public BankAccount(String accountNumber) {
        this.accountNumber = accountNumber;
        this.balance = 0.0; // Initial balance is zero
    }

    // Public method to deposit money
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            System.out.println("Deposit amount must be positive.");
        }
    }

    // Public method to withdraw money
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        } else {
            System.out.println("Insufficient balance or invalid amount.");
        }
    }

    // Public method to check the balance
    public double getBalance() {
        return balance;
    }
}

// Using the class in the main method
public class Main {
    public static void main(String[] args) {
        // Creating a new BankAccount object
        BankAccount myAccount = new BankAccount("123456789");

        // Depositing money
        myAccount.deposit(500.0);
        System.out.println("Balance after deposit: " + myAccount.getBalance()); // Output: 500.0

        // Withdrawing money
        myAccount.withdraw(200.0);
        System.out.println("Balance after withdrawal: " + myAccount.getBalance()); // Output: 300.0

        // Attempting to withdraw more than the balance
        myAccount.withdraw(400.0); // Output: Insufficient balance or invalid amount.
    }
}
```
---
# What is Inheritance?

Inheritance is a fundamental concept in object-oriented programming that allows one class to inherit properties and methods from another class. This promotes code reusability and establishes a relationship between classes.

## Types of Inheritance

### 1. Single Inheritance
- **Definition**: A subclass inherits from one superclass.
- **Example**:
    ```java
    class Animal {
        void eat() {
            System.out.println("Eating...");
        }
    }

    class Dog extends Animal {
        void bark() {
            System.out.println("Barking...");
        }
    }
    ```

### 2. Multiple Inheritance
- **Definition**: A subclass can inherit from multiple superclasses. (Note: Not directly supported in Java; can be achieved through interfaces.)
- **Example** (using interfaces):
    ```java
    interface CanRun {
        void run();
    }

    interface CanBark {
        void bark();
    }

    class Dog implements CanRun, CanBark {
        public void run() {
            System.out.println("Running...");
        }

        public void bark() {
            System.out.println("Barking...");
        }
    }
    ```

### 3. Multilevel Inheritance
- **Definition**: A subclass inherits from a superclass, which is also a subclass of another class.
- **Example**:
    ```java
    class Animal {
        void eat() {
            System.out.println("Eating...");
        }
    }

    class Dog extends Animal {
        void bark() {
            System.out.println("Barking...");
        }
    }

    class Puppy extends Dog {
        void weep() {
            System.out.println("Weeping...");
        }
    }
    ```

### 4. Hierarchical Inheritance
- **Definition**: Multiple subclasses inherit from a single superclass.
- **Example**:
    ```java
    class Animal {
        void eat() {
            System.out.println("Eating...");
        }
    }

    class Dog extends Animal {
        void bark() {
            System.out.println("Barking...");
        }
    }

    class Cat extends Animal {
        void meow() {
            System.out.println("Meowing...");
        }
    }
    ```

### 5. Hybrid Inheritance
- **Definition**: A combination of two or more types of inheritance. (Not directly supported in Java due to the complexity it may introduce.)
- **Example** (conceptual):
    ```java
    class Animal {
        void eat() {}
    }

    interface CanRun {
        void run();
    }

    class Dog extends Animal implements CanRun {
        void bark() {}
        public void run() {}
    }

    class Cat extends Animal {
        void meow() {}
    }
    ```

---
---

# What is Abstraction?

Abstraction is one of the core principles of object-oriented programming (OOP). It allows the programmer to focus on essential features of an object while hiding the unnecessary details.

## Key Concepts of Abstraction

1. **Definition**: 
   - Abstraction involves creating simple models that represent complex real-world entities. It allows users to interact with an object without needing to understand the internal workings of that object.

2. **Purpose**: 
   - To reduce complexity by hiding the implementation details and showing only the essential features of the object.
   - To enhance code reusability and flexibility.

## How to Achieve Abstraction

### 1. Abstract Classes
- An abstract class is a class that cannot be instantiated and is declared using the `abstract` keyword.
- It can contain both abstract methods (without implementation) and concrete methods (with implementation).

**Example**:
```java
abstract class Shape {
    abstract void draw(); // Abstract method

    void display() { // Concrete method
        System.out.println("Displaying shape");
    }
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing Circle");
    }
}
```
### 2. Interfaces
- An interface is a reference type in Java that can contain only constants, method signatures, default methods, static methods, and nested types.
- Interfaces are used to achieve full abstraction.
```java
interface Animal {
    void eat(); // Abstract method
}

class Dog implements Animal {
    public void eat() {
        System.out.println("Dog is eating");
    }
}
```
---
# What is Polymorphism?

Polymorphism is a fundamental concept in object-oriented programming (OOP) that allows methods to do different things based on the object it is acting upon. The term "polymorphism" means "many shapes" and refers to the ability of a single interface to represent different types or forms.

## Types of Polymorphism

### 1. Compile-Time Polymorphism (Static Binding)

- **Definition**: This type of polymorphism is resolved during compile time. It is achieved through method overloading and operator overloading.
  
- **Method Overloading**: Occurs when multiple methods in the same class have the same name but different parameters (different type, number, or both).

**Example**:
```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```
### 2. Run-Time Polymorphism (Dynamic Binding)
- **Definition**: This type of polymorphism is resolved during runtime. It is achieved through method overriding.

- **Method Overriding**: Occurs when a subclass provides a specific implementation of a method that is already defined in its superclass.
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class TestPolymorphism {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        Animal myCat = new Cat();
        myDog.sound(); // Outputs: Dog barks
        myCat.sound(); // Outputs: Cat meows
    }
}
```
### Benefits of Polymorphism
- Code Reusability: The same method name can be used for different types, leading to cleaner and more maintainable code.
- Flexibility: Allows for easy extension and modification of existing code.
- Dynamic Method Resolution: Enables runtime decision making, which enhances the functionality of the program.
---







