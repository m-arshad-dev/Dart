# 🧩 Mixins & Extensions in Dart

In Dart, **Mixins** and **Extensions** allow you to **reuse code** and **extend functionality** without traditional inheritance.  
Let’s explore both step-by-step 👇

---

## 🧱 1. Mixins — Reuse Code Across Classes

### 🔹 What is a Mixin?

A **mixin** is a class whose methods can be used by other classes **without being their parent**.

You use the `with` keyword to add a mixin’s behavior to a class.

### ✅ Example: Using a Mixin

```dart
mixin Logger {
  void log(String message) {
    print('LOG: $message');
  }
}

class Vehicle {
  void start() => print('Vehicle started');
}

class Car extends Vehicle with Logger {
  void drive() {
    log('Car is driving...');
  }
}

void main() {
  Car car = Car();
  car.start();
  car.drive();
}
```

**Output:**
```
Vehicle started
LOG: Car is driving...
```

### 🧠 How It Works
- The `Car` class **inherits** methods from `Vehicle`.
- It also **mixes in** methods from `Logger` using `with`.
- This avoids deep inheritance chains.

### ⚙️ Mixin Rules
- A mixin **cannot** have a constructor.
- A mixin can be applied to **multiple classes**.
- Mixins can be **restricted** to certain types using `on`.

#### Example: Restricting Mixins

```dart
class Animal {
  void move() => print('Animal is moving');
}

mixin Swimmer on Animal {
  void swim() => print('Swimming...');
}

class Fish extends Animal with Swimmer {}

void main() {
  Fish f = Fish();
  f.move();
  f.swim();
}
```

The `Swimmer` mixin can only be used on classes that **extend `Animal`**.

---

## 🔧 2. Extensions — Add Features to Existing Classes

### 🔹 What is an Extension?

An **extension** lets you **add new methods or getters** to an existing class **without modifying it**.

This is helpful for built-in classes (like `String`, `int`, etc.) or third-party types.

### ✅ Example: Add Method to String

```dart
extension StringUtils on String {
  bool get isPalindrome {
    String clean = replaceAll(' ', '').toLowerCase();
    return clean == clean.split('').reversed.join('');
  }
}

void main() {
  print('level'.isPalindrome); // true
  print('hello'.isPalindrome); // false
}
```

Now every `String` object has an `.isPalindrome` property!

---

### ⚙️ Example: Extension with Functions

```dart
extension NumberUtils on int {
  bool get isEvenNumber => this % 2 == 0;

  int square() => this * this;
}

void main() {
  print(4.isEvenNumber); // true
  print(5.square());     // 25
}
```

---

### 💡 Naming Extensions

You can give your extensions names (recommended for large projects):

```dart
extension FancyStringUtils on String { ... }
```

Then, if name conflicts occur (e.g., two extensions define the same method),  
you can call it explicitly:

```dart
FancyStringUtils('dart').isPalindrome;
```

---

## 🧭 Mixins vs Extensions — Quick Comparison

| Feature | Mixins | Extensions |
|----------|---------|------------|
| Purpose | Reuse behavior in **classes** | Add new features to **existing types** |
| Keyword | `with` | `extension` |
| Can have state? | ✅ Yes (fields, methods) | ❌ No (only methods/getters/setters) |
| Constructors allowed? | ❌ No | ❌ No |
| Example use | `with Logger` | `myString.isPalindrome` |

---

## 🧩 Summary

- **Mixins** → Reuse methods across multiple classes.  
  → Use `mixin` + `with`.
- **Extensions** → Add functionality to existing types.  
  → Use `extension` + `on`.

Both are **powerful tools** for writing **clean, reusable, and scalable Dart code** 🚀

---

✅ **Next Step:**  
Learn about **Generics** → how to write flexible, type-safe Dart code.
