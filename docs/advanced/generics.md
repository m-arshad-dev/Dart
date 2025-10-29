# 🧩 Generics in Dart

Generics allow you to **write flexible, reusable, and type-safe code**.  
They let you define classes, methods, and collections that can work with **any data type** — while still catching type errors **at compile time**.

---

## 🔍 Why Use Generics?

Without generics, you lose type safety:

```dart
List numbers = [1, 2, 3];
numbers.add('four'); // ❌ No compile-time error
```

With generics:

```dart
List<int> numbers = [1, 2, 3];
numbers.add('four'); // ❌ Compile-time error
```

✅ Generics help:
- Prevent type-related bugs.
- Make code reusable and consistent.
- Improve readability and performance (no `dynamic` boxing).

---

## 🧱 Generic Collections

All Dart collections (like `List`, `Set`, and `Map`) are **generic**.

```dart
List<String> names = ['Ali', 'Sara'];
Set<int> ids = {1, 2, 3};
Map<String, int> scores = {'Ali': 90, 'Sara': 95};
```

You can also use **nested generics**:

```dart
Map<String, List<int>> marks = {
  'Ali': [80, 90],
  'Sara': [85, 95],
};
```

---

## 🧰 Generic Classes

You can create your own **generic class** using `<T>`:

```dart
class Box<T> {
  T value;
  Box(this.value);

  void show() {
    print('Value: $value');
  }
}

void main() {
  var intBox = Box<int>(10);
  var strBox = Box<String>('Hello');

  intBox.show(); // Output: Value: 10
  strBox.show(); // Output: Value: Hello
}
```

Here, `T` is a **type parameter** — you decide its actual type when creating an object.

---

## 🔧 Generic Functions

Functions can also be generic:

```dart
T pickFirst<T>(T a, T b) {
  return a;
}

void main() {
  print(pickFirst<int>(10, 20)); // 10
  print(pickFirst<String>('Hi', 'Bye')); // Hi
}
```

If Dart can **infer** the type, you don’t need to specify it:

```dart
print(pickFirst('Hello', 'World')); // Automatically <String>
```

---

## 🧭 Type Constraints (`extends`)

You can **restrict** generic types using `extends`.

Example: only allow numbers.

```dart
class Calculator<T extends num> {
  T add(T a, T b) => (a + b) as T;
}

void main() {
  var calc = Calculator<int>();
  print(calc.add(10, 20)); // 30

  // var bad = Calculator<String>(); ❌ Error: String is not a subtype of num
}
```

---

## 🧩 Multiple Type Parameters

You can define more than one generic type:

```dart
class Pair<K, V> {
  K key;
  V value;

  Pair(this.key, this.value);
}

void main() {
  var pair = Pair<String, int>('Age', 25);
  print('${pair.key}: ${pair.value}');
}
```

---

## 🧠 Best Practices

✅ Use generics when:
- You work with collections or reusable components.
- You want compile-time type checking.

🚫 Avoid overusing them when:
- Simplicity is more important than flexibility.
- You don’t need multiple data types.

---

## 🧾 Summary

| Concept | Example | Description |
|----------|----------|-------------|
| Generic List | `List<int>` | Type-safe collection |
| Generic Class | `class Box<T>` | Works with any type |
| Generic Function | `T getItem<T>()` | Type-safe function |
| Type Constraint | `<T extends num>` | Restrict types |
| Multiple Parameters | `<K, V>` | For key–value patterns |

---

🎯 **In short:**  
Generics make Dart code **type-safe**, **clean**, and **reusable** — a must-know for advanced Dart programming.
