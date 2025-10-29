# 🧮 Dart Operators

Operators in Dart are special symbols used to perform operations on variables and values.

---

## 1. Arithmetic Operators

Used to perform basic mathematical operations.

| Operator | Description | Example | Result |
|-----------|--------------|----------|---------|
| `+` | Addition | `10 + 5` | `15` |
| `-` | Subtraction | `10 - 5` | `5` |
| `*` | Multiplication | `10 * 5` | `50` |
| `/` | Division (returns double) | `10 / 3` | `3.3333` |
| `~/` | Integer Division | `10 ~/ 3` | `3` |
| `%` | Modulus (remainder) | `10 % 3` | `1` |

```dart
void main() {
  var a = 10, b = 3;
  print(a + b);   // 13
  print(a ~/ b);  // 3
  print(a % b);   // 1
}
```

---

## 2. Relational Operators

Used to compare two values (result is `true` or `false`).

| Operator | Description              | Example  | Result  |
| -------- | ------------------------ | -------- | ------- |
| `==`     | Equal to                 | `5 == 5` | `true`  |
| `!=`     | Not equal to             | `5 != 3` | `true`  |
| `>`      | Greater than             | `5 > 3`  | `true`  |
| `<`      | Less than                | `5 < 3`  | `false` |
| `>=`     | Greater than or equal to | `5 >= 5` | `true`  |
| `<=`     | Less than or equal to    | `3 <= 5` | `true`  |

```dart
void main() {
  var x = 5, y = 3;
  print(x > y);  // true
}
```

---

## 3. Logical Operators

Used to combine conditional expressions.

| Operator | Description | Example | Result |
| -------- | ----------- | -------- | ------- |
| `&&` | Logical AND | `(x > 0 && y > 0)` | true if both are true |
| `||` | Logical OR | `(x > 0 || y > 0)` | true if any one is true |
| `!` | Logical NOT | `!(x > 0)` | reverses the result |

```dart
void main() {
  var x = 5, y = -2;
  print(x > 0 && y > 0); // false
  print(x > 0 || y > 0); // true
  print(!(x > 0));       // false
}
```

---

## 4. Assignment Operators

Used to assign values to variables.

| Operator | Example   | Meaning        |
| -------- | --------- | -------------- |
| `=`      | `a = 5`   | Assigns 5 to a |
| `+=`     | `a += 2`  | a = a + 2      |
| `-=`     | `a -= 2`  | a = a - 2      |
| `*=`     | `a *= 2`  | a = a * 2      |
| `/=`     | `a /= 2`  | a = a / 2      |
| `~/=`    | `a ~/= 2` | a = a ~/ 2     |

```dart
void main() {
  var n = 10;
  n += 5;
  print(n); // 15
}
```

---

## 5. Type Test Operators

Used to check object types.

| Operator | Description | Example |
| -------- | ------------ | -------- |
| `is` | Returns true if object is of a specified type | `x is int` |
| `is!` | Returns true if object is *not* of a specified type | `x is! String` |

```dart
void main() {
  var name = "Dart";
  print(name is String); // true
  print(name is! int);   // true
}
```

---

## 6. Null-Aware Operators

Used to handle `null` values safely.

| Operator | Description | Example | Meaning |
| -------- | ------------ | -------- | -------- |
| `??` | Default value if null | `x ?? 10` | if `x` is null → use 10 |
| `??=` | Assign if null | `x ??= 5` | assigns 5 only if `x` is null |
| `?.` | Access property safely | `obj?.name` | returns null if obj is null |

```dart
void main() {
  int? a;
  a ??= 10;       // assign 10 if a is null
  print(a);       // 10
}
```

---

## 7. Conditional Operator (Ternary)

Used to shorten `if-else` statements.

```dart
void main() {
  var score = 70;
  var result = (score >= 50) ? 'Pass' : 'Fail';
  print(result); // Pass
}
```

---

## 8. Cascade Operator (`..`)

Allows chaining multiple operations on the same object.

```dart
class Student {
  String? name;
  int? age;
}

void main() {
  var s = Student()
    ..name = 'Ali'
    ..age = 21;
    
  print('Name: ${s.name}, Age: ${s.age}');
}
```

---

## ✅ Summary

Operators make your Dart code concise and expressive — from simple math to handling nulls and chaining methods efficiently.

---

## 🧠 Practice Tasks

Try these small exercises to strengthen your understanding:

1. **Even or Odd:**  
   Write a program that checks if a number is even or odd using the modulus operator (`%`).

2. **Pass or Fail:**  
   Use a ternary operator to print `"Pass"` if marks ≥ 50, otherwise `"Fail"`.

3. **Null Handling:**  
   Create a nullable variable `String? name;` and print `"Guest"` if it’s null using `??`.

4. **Type Check:**  
   Write a condition to check if a variable `x` is a `double` using the `is` operator.

---

🎯 **Next:** Learn about [Control Flow Statements](control-flow.md) → to see how these operators work in real-world code.
