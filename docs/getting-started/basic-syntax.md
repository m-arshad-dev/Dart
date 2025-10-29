# 📝 Dart Basic Syntax

Before diving deep, let’s understand how Dart code is structured and written.

---

## 1. Your First Dart Program

```dart
void main() {
  print('Hello, Dart!');
}
```

**Explanation:**
- `void main()` → The entry point of every Dart program.
- `print()` → Displays output to the console.

---

## 2. Comments

```dart
// Single-line comment

/* Multi-line
   comment */

/**
 * Documentation comment
 */
```

---

## 3. Variables

Variables store data. Dart is **statically typed**, but supports **type inference**.

```dart
var name = 'Arshad';   // Type inferred as String
int age = 25;
double pi = 3.14;
bool isActive = true;
```

**Constants:**
```dart
const speedOfLight = 299792458; // Compile-time constant
final currentTime = DateTime.now(); // Runtime constant
```

---

## 4. Data Types

| Type | Example | Description |
|------|----------|-------------|
| `int` | `10` | Integer values |
| `double` | `3.14` | Decimal numbers |
| `String` | `'Hello'` | Text values |
| `bool` | `true`, `false` | Logical values |
| `List` | `[1, 2, 3]` | Ordered collection |
| `Map` | `{'key': 'value'}` | Key-value pairs |
| `Set` | `{1, 2, 3}` | Unique values |

---

## 5. String Operations

```dart
var first = 'Dart';
var second = 'Language';

print('$first $second');   // String interpolation
print(first + ' ' + second);
print('Length: ${first.length}');
```

---

## 6. Operators

```dart
// Arithmetic
var sum = 10 + 5;
var product = 10 * 2;

// Comparison
print(5 > 3);   // true
print(5 == 5);  // true

// Logical
print(true && false); // false

// Null-aware
var name;
print(name ?? 'Guest'); // Prints 'Guest'
```

---

## 7. Control Flow

### If–Else
```dart
if (age >= 18) {
  print('Adult');
} else {
  print('Minor');
}
```

### Loops
```dart
for (var i = 0; i < 3; i++) {
  print(i);
}

while (age < 30) {
  print('Still young!');
  age++;
}

do {
  print('This runs at least once');
} while (false);
```

### Switch
```dart
var grade = 'A';
switch (grade) {
  case 'A':
    print('Excellent');
    break;
  case 'B':
    print('Good');
    break;
  default:
    print('Try again');
}
```

---

## 8. Functions

```dart
int add(int a, int b) {
  return a + b;
}

void greet(String name) => print('Hello, $name');
```

---

## 9. Null Safety

Dart uses **null safety** — variables can’t be null unless declared nullable.

```dart
int? number = null;  // Nullable
int count = 10;      // Non-nullable
```

---

## 10. Collections

### Lists
```dart
var fruits = ['apple', 'banana'];
fruits.add('mango');
print(fruits[0]); // apple
```

### Maps
```dart
var user = {'name': 'Arshad', 'age': 25};
print(user['name']); // Arshad
```

### Sets
```dart
var numbers = {1, 2, 2, 3};
print(numbers); // {1, 2, 3}
```

---

## ✅ Summary

| Concept | Example |
|----------|----------|
| Entry point | `void main()` |
| Variable | `var x = 10;` |
| Function | `int add(int a, int b)` |
| Conditional | `if`, `else`, `switch` |
| Loop | `for`, `while`, `do` |
| Collections | `List`, `Map`, `Set` |
| Null Safety | `int? x = null` |

---

> 🔹 Next Step → Learn about **Operators** or **Control Flow in Depth**
