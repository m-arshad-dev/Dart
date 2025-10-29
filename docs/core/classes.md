# 🧱 Dart Classes and Object-Oriented Programming (OOP)

Dart is an **object-oriented language**, meaning everything is an object — even numbers and functions.  
Objects are created from **classes**, which define how they look and behave.

---

## 🧩 What is a Class?

A **class** is a blueprint for creating objects (instances).

```dart
class Person {
  String name;
  int age;

  // Constructor
  Person(this.name, this.age);

  // Method
  void introduce() {
    print('Hi, I\'m $name and I\'m $age years old.');
  }
}

void main() {
  var p1 = Person('Arshad', 25);
  p1.introduce();
}
```

### ✅ Output
```
Hi, I'm Arshad and I'm 25 years old.
```

---

## 🏗️ Constructors

Constructors create new objects.  
There are several types:

### 1. Default Constructor
```dart
class Car {
  String brand;
  Car(this.brand);
}
```

### 2. Named Constructor
```dart
class Car {
  String brand;
  Car(this.brand);
  Car.electric() {
    brand = 'Tesla';
  }
}
```

### 3. Redirecting Constructor
```dart
class Car {
  String brand;
  Car(this.brand);
  Car.defaultBrand() : this('Toyota');
}
```

### 4. Constant Constructor (for immutable objects)
```dart
class Point {
  final int x, y;
  const Point(this.x, this.y);
}
```

---

## 🧱 Instance Variables & Methods

Instance variables belong to objects.

```dart
class Dog {
  String name;
  void bark() => print('$name says woof!');
}
```

---

## ⚙️ Getters and Setters

They control access to private variables (`_variable`).

```dart
class BankAccount {
  double _balance = 0;

  double get balance => _balance;
  set deposit(double amount) => _balance += amount;
}
```

---

## 🧰 Static Members

Used when a variable or method belongs to the **class**, not objects.

```dart
class MathUtil {
  static const pi = 3.1416;
  static double square(num n) => n * n;
}

void main() {
  print(MathUtil.square(5));
}
```

---

## 🧬 Inheritance

Classes can inherit from other classes using `extends`.

```dart
class Animal {
  void eat() => print('Animal eats');
}

class Dog extends Animal {
  void bark() => print('Dog barks');
}

void main() {
  var d = Dog();
  d.eat();
  d.bark();
}
```

---

## 🔁 Method Overriding

You can override parent methods using `@override`.

```dart
class Animal {
  void sound() => print('Some sound');
}

class Cat extends Animal {
  @override
  void sound() => print('Meow!');
}
```

---

## 🧩 Super Keyword

Used to access the parent class.

```dart
class Vehicle {
  Vehicle() {
    print('Vehicle created');
  }
}

class Car extends Vehicle {
  Car() : super() {
    print('Car created');
  }
}
```

---

## 🧠 Abstract Classes

Used as **blueprints** that cannot be instantiated directly.

```dart
abstract class Shape {
  void draw(); // abstract method
}

class Circle extends Shape {
  @override
  void draw() => print('Drawing circle');
}
```

---

## ⚡ Interfaces

All classes implicitly define an interface.  
Use `implements` to enforce behavior.

```dart
class Printer {
  void printDoc() {}
}

class HPPrinter implements Printer {
  @override
  void printDoc() => print('Printing document...');
}
```

---

## 🧩 Mixins

Mixins let you reuse code across multiple classes.

```dart
mixin Swimmer {
  void swim() => print('Can swim');
}

class Fish with Swimmer {}
class Human with Swimmer {}
```

---

## 🧰 Enums with Classes

Enums define constant sets of values.

```dart
enum Status { success, failure, loading }

class Response {
  final Status status;
  Response(this.status);
}
```

---

## 🧱 Object Class (Base Class of All)

All Dart classes inherit from `Object`, which provides:
- `toString()`
- `hashCode`
- `==` (can be overridden)

```dart
class User {
  String name;
  User(this.name);

  @override
  String toString() => 'User(name: $name)';
}
```

---

## 🧠 Summary

| Concept | Description | Keyword |
|----------|--------------|---------|
| Class | Blueprint for objects | `class` |
| Object | Instance of class | `new` (optional) |
| Inheritance | Reuse from parent class | `extends` |
| Interface | Defines contract | `implements` |
| Abstract | Blueprint only | `abstract` |
| Mixin | Share reusable code | `mixin`, `with` |
| Static | Belongs to class | `static` |

---

## 🧩 Quick Practice

Try this mini challenge 👇

```dart
abstract class Animal {
  void makeSound();
}

mixin Runner {
  void run() => print('Running fast!');
}

class Dog extends Animal with Runner {
  @override
  void makeSound() => print('Woof!');
}

void main() {
  var d = Dog();
  d.makeSound();
  d.run();
}
```

✅ Output:
```
Woof!
Running fast!
```

---

> 🔍 **Next step:** Learn about **asynchronous programming (Futures, async, await)** in Dart.
