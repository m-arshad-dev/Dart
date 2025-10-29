# 🔄 Control Flow in Dart

Control flow statements decide **how your program executes** — whether it repeats actions, skips sections, or makes decisions.

---

## 🧠 1. Conditional Statements

### `if` / `else if` / `else`

Used to execute code based on conditions.

```dart
void main() {
  int age = 20;

  if (age >= 18) {
    print('You are an adult.');
  } else if (age > 13) {
    print('You are a teenager.');
  } else {
    print('You are a child.');
  }
}
```

💡 **Tip:** Conditions in Dart must return a `bool`.

---

## 🔁 2. Loops

### `for` Loop
Used when you know how many times to repeat.

```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    print('Count: $i');
  }
}
```

### `for-in` Loop
Used to iterate over collections like lists.

```dart
void main() {
  var fruits = ['apple', 'banana', 'mango'];
  for (var fruit in fruits) {
    print(fruit);
  }
}
```

### `while` Loop
Repeats while a condition is true.

```dart
void main() {
  int count = 1;
  while (count <= 3) {
    print('While loop: $count');
    count++;
  }
}
```

### `do-while` Loop
Runs **at least once**, even if the condition is false.

```dart
void main() {
  int num = 3;
  do {
    print('Number: $num');
    num--;
  } while (num > 0);
}
```

---

## 🧭 3. `break` and `continue`

- **`break`** exits a loop immediately.  
- **`continue`** skips the current iteration.

```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    if (i == 3) continue; // skip 3
    if (i == 5) break;    // stop at 5
    print(i);
  }
}
```

---

## ⚙️ 4. `switch` Statement

Used when comparing one variable to multiple values.

```dart
void main() {
  String grade = 'B';

  switch (grade) {
    case 'A':
      print('Excellent!');
      break;
    case 'B':
      print('Good job!');
      break;
    case 'C':
      print('You passed.');
      break;
    default:
      print('Invalid grade.');
  }
}
```

💡 **Note:** Each case must end with `break`, `return`, or `continue` (to prevent fall-through).

---

## 🧩 5. `assert` Statement

Used for **debug checks** — throws an error if the condition is false.

```dart
void main() {
  int age = 15;
  assert(age >= 18, 'Age must be at least 18!');
  print('Adult verified.');
}
```

✅ Runs only in **debug mode**, not in production.

---

## 🛠️ 6. Exception Handling (`try`, `catch`, `finally`)

Handle runtime errors gracefully.

```dart
void main() {
  try {
    int result = 10 ~/ 0; // division by zero
  } catch (e) {
    print('Error: $e');
  } finally {
    print('This always runs.');
  }
}
```

---

## 🚀 Summary

| Concept | Purpose |
|----------|----------|
| `if / else` | Decision making |
| `for / while / do-while` | Repetition |
| `break / continue` | Loop control |
| `switch` | Multi-branch decision |
| `assert` | Debug validation |
| `try-catch-finally` | Error handling |

---

**Next:** [Functions in Dart →](functions.md)
