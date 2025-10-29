---
title: Variables and Data Types in Dart
description: Learn how to declare variables, understand Dart data types, and work with constants, lists, maps, and sets in Dart programming.
---

# 🧠 Variables and Data Types in Dart

Understanding **variables** and **data types** is the foundation of any programming language — and Dart is no exception.  
Let’s explore what they are, how to use them, and how Dart makes them both **powerful** and **simple**.

---

## 🪜 Step 1: What Is a Variable?

A **variable** is like a container that stores a value — it gives data a name so you can use it in your program.

> 🧺 **Variable = Label + Value**

### 💡 Example

```dart
void main() {
  var name = 'Arshad';
  print(name);
}
```

**Output:**

```
Arshad
```

**Explanation:**

| Part | Meaning |
|------|----------|
| `name` | Variable name |
| `'Arshad'` | Value assigned |
| `var` | Dart automatically infers the type (`String` in this case) |

---

## 🧩 Step 2: Declaring Variables

There are multiple ways to declare variables in Dart, each with a specific purpose.

| Keyword | Description | Example |
|----------|--------------|----------|
| `var` | Type inferred automatically | `var age = 20;` |
| `dynamic` | Type can change later | `dynamic data = 'Hello'; data = 123;` |
| `final` | Immutable after assignment (runtime constant) | `final city = 'Lahore';` |
| `const` | Immutable at compile time | `const PI = 3.14;` |
| Explicit Type | Declare with a specific type | `int year = 2025;` |

---

## ⚡ Step 3: Understanding Dart Data Types

Dart is **statically typed**, meaning every variable has a specific type — even when Dart infers it for you.

---

### 🔢 Numbers

Dart supports two main number types:

- `int` → for integers (whole numbers)  
- `double` → for decimal numbers  

#### Example

```dart
void main() {
  int age = 25;
  double price = 9.99;

  print('Age: $age');
  print('Price: $price');
}
```

**Output:**

```
Age: 25
Price: 9.99
```

✅ You can also use `num` (can store both `int` and `double`):

```dart
num total = 100.5;
```

---

### 🧵 Strings

Strings represent text.

```dart
void main() {
  String name = 'Arshad';
  String greeting = 'Hello, $name!'; // String interpolation
  print(greeting);
}
```

**Output:**

```
Hello, Arshad!
```

!!! tip "String Tips"
- Use `' '` or `" "` — both work.  
- Use triple quotes (`'''` or `"""`) for **multi-line strings**.  
- Use **interpolation** (`$variable` or `${expression}`) for string combination.  

---

### ⚙️ Booleans (`bool`)

Represents **true** or **false** values.

```dart
void main() {
  bool isActive = true;
  bool isLoggedIn = false;

  print(isActive);
  print(isLoggedIn);
}
```

**Output:**

```
true
false
```

✅ Used often in conditions:

```dart
if (isActive) {
  print('User is active!');
}
```

---

### 🧺 Lists (Arrays)

A **List** stores multiple values in an ordered sequence.

```dart
void main() {
  List<String> fruits = ['Apple', 'Banana', 'Mango'];
  print(fruits);
  print(fruits[1]); // Access by index
}
```

**Output:**

```
[Apple, Banana, Mango]
Banana
```

✅ Modify lists dynamically:

```dart
fruits.add('Orange');
fruits.remove('Banana');
```

!!! note
Lists in Dart are **zero-indexed** — meaning the first element is at index `0`.

---

### 🗺️ Maps (Key–Value Pairs)

Maps store data as **key → value** pairs, similar to dictionaries in other languages.

```dart
void main() {
  Map<String, String> user = {
    'name': 'Arshad',
    'city': 'Lahore',
    'country': 'Pakistan',
  };

  print(user['name']); // Access by key
}
```

**Output:**

```
Arshad
```

!!! tip
Maps are excellent for representing structured data — such as user profiles or configuration settings.

---

### 🔢 Sets

A **Set** is an unordered collection of **unique** values (no duplicates).

```dart
void main() {
  Set<int> numbers = {1, 2, 3, 3, 2};
  print(numbers);
}
```

**Output:**

```
{1, 2, 3}
```

---

## 🧱 Step 4: Type Inference — `var` vs `dynamic`

### `var`

```dart
var name = 'Arshad';  // inferred as String
name = 'Ali';         // ✅ allowed
// name = 10;         // ❌ Error: cannot assign int to String
```

### `dynamic`

```dart
dynamic variable = 'Hello';
variable = 123;       // ✅ Works
variable = true;      // ✅ Works
```

!!! tip
Use:
- `var` → when type **does not change**.  
- `dynamic` → when type **may change** during runtime.

---

## 🔒 Step 5: Constants — `final` vs `const`

Both create **immutable variables**.

| Keyword | When to Use | Example |
|----------|--------------|----------|
| `final` | Value known **at runtime** | `final now = DateTime.now();` |
| `const` | Value known **at compile-time** | `const pi = 3.1416;` |

#### Example

```dart
void main() {
  final today = DateTime.now(); // runtime constant
  const version = 1.0;          // compile-time constant
}
```

---

## 🔄 Step 6: Type Conversion

Convert between types easily:

```dart
void main() {
  // String → int
  int a = int.parse('10');

  // String → double
  double b = double.parse('12.5');

  // int → String
  String c = a.toString();

  // double → int
  int d = b.toInt();

  print('$a, $b, $c, $d');
}
```

**Output:**

```
10, 12.5, 10, 12
```

---

## 📚 Step 7: Summary Table

| Type | Description | Example |
|------|--------------|----------|
| `int` | Whole numbers | `int age = 20;` |
| `double` | Decimal numbers | `double price = 10.5;` |
| `String` | Text | `String name = 'Dart';` |
| `bool` | True/False | `bool isOk = true;` |
| `List` | Ordered collection | `List<int> nums = [1, 2, 3];` |
| `Map` | Key-value pairs | `Map user = {'id': 1};` |
| `Set` | Unique values | `Set<int> s = {1, 2, 3};` |
| `var` | Type inferred automatically | `var name = 'Ali';` |
| `dynamic` | Type flexible | `dynamic x = 10; x = 'Hi';` |
| `final` | Immutable (runtime) | `final city = 'Lahore';` |
| `const` | Immutable (compile time) | `const PI = 3.14;` |

---

## 🧩 Practice Exercise

Try this small challenge 👇

```dart
void main() {
  var name = 'Arshad';
  int age = 25;
  double height = 5.9;
  bool isStudent = true;
  List<String> skills = ['Dart', 'Flutter', 'Git'];
  Map<String, String> address = {'city': 'Lahore', 'country': 'Pakistan'};

  print('My name is $name, I am $age years old.');
  print('Height: $height ft');
  print('Am I a student? $isStudent');
  print('Skills: $skills');
  print('Address: $address');
}
```

**Expected Output:**

```
My name is Arshad, I am 25 years old.
Height: 5.9 ft
Am I a student? true
Skills: [Dart, Flutter, Git]
Address: {city: Lahore, country: Pakistan}
```

---

## 🧠 Quick Recap

- Dart automatically **infers variable types** with `var`.  
- Use `dynamic` for variables that can hold different types.  
- Use `final` or `const` for **immutable** values.  
- Core built-in types: `int`, `double`, `String`, `bool`, `List`, `Map`, and `Set`.  
- Everything in Dart is an **object**, even numbers and booleans.  

---

<div class="grid cards" markdown>

- [:material-arrow-left-circle: Previous — Hello World](../getting-started/hello-world.md)
- [:material-arrow-right-circle: Next — Operators in Dart](operators.md)

</div>
