# 🧩 Dart Functions

Functions are blocks of code that perform a specific task. They help make code **reusable**, **organized**, and **readable**.

---

## 🔹 1. Defining a Function

```dart
void greet() {
  print('Hello, Dart!');
}
```

- `void` → return type (means it returns nothing)
- `greet()` → function name
- `{ ... }` → function body

### Calling a Function
```dart
greet(); // Output: Hello, Dart!
```

---

## 🔹 2. Function with Parameters

```dart
void greetUser(String name) {
  print('Hello, $name!');
}

greetUser('Arshad'); // Output: Hello, Arshad!
```

---

## 🔹 3. Function with Return Value

```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print(add(3, 5)); // Output: 8
}
```

---

## 🔹 4. Arrow (=>) Functions

For short functions, Dart provides a concise syntax.

```dart
int square(int n) => n * n;
String greet(String name) => 'Hello, $name!';
```

---

## 🔹 5. Optional & Default Parameters

### ➤ Positional Optional Parameters
Use square brackets `[ ]`:

```dart
void showInfo(String name, [int? age]) {
  print('Name: $name');
  if (age != null) print('Age: $age');
}

showInfo('Ali');
showInfo('Ali', 22);
```

### ➤ Named Optional Parameters
Use curly braces `{ }`:

```dart
void userInfo({String? name, int? age}) {
  print('Name: $name, Age: $age');
}

userInfo(name: 'Ayesha', age: 25);
```

### ➤ Default Values
```dart
void greet({String name = 'Guest'}) {
  print('Welcome, $name!');
}

greet();           // Welcome, Guest!
greet(name: 'Ali'); // Welcome, Ali!
```

---

## 🔹 6. Anonymous Functions (Lambdas)

Functions without a name — often used in callbacks.

```dart
var numbers = [1, 2, 3];
numbers.forEach((num) {
  print(num * 2);
});
```

Or using arrow syntax:
```dart
numbers.forEach((num) => print(num * 2));
```

---

## 🔹 7. Higher-Order Functions

A **higher-order function** takes another function as a parameter or returns one.

```dart
void process(int n, Function func) {
  print(func(n));
}

int doubleIt(int n) => n * 2;

process(5, doubleIt); // Output: 10
```

---

## 🔹 8. Lexical Scope & Closures

Functions can access variables from the outer scope.

```dart
Function makeAdder(int addBy) {
  return (int i) => i + addBy;
}

var add2 = makeAdder(2);
print(add2(5)); // Output: 7
```

---

## 🔹 9. Anonymous + Arrow Function Example

```dart
List<int> nums = [1, 2, 3, 4];
var doubled = nums.map((n) => n * 2);
print(doubled.toList()); // [2, 4, 6, 8]
```

---

## 🔹 10. Main Function

Every Dart program starts from the `main()` function.

```dart
void main() {
  print('Program started!');
}
```

---

## 🧠 Summary

| Type | Example | Notes |
|------|----------|-------|
| Basic | `void greet() {}` | No parameters or return value |
| With Params | `void greet(String name)` | Accepts input |
| Return | `int add(int a, int b)` | Returns value |
| Arrow | `int square(int n) => n * n;` | Short syntax |
| Optional | `void info([int? age])` | Optional arguments |
| Named | `void info({String? name})` | Named args |
| Higher-order | `process(5, doubleIt)` | Pass/return functions |
| Closure | `makeAdder(2)` | Keeps access to outer scope |

---

✅ **Next Step:** Learn about **async functions** and `Future`, `await`, `async` in Dart (for asynchronous programming).

