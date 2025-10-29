# 👋 Hello World in Dart

Your first step into Dart programming starts with the classic **“Hello, World!”** example.  
This simple program introduces you to Dart syntax and how to run Dart code.

---

## 🧠 What Is “Hello World”?

“Hello World” is traditionally the first program written in any language.  
It prints a simple message to the screen — helping you test that your setup works correctly.

---

## ⚙️ Step 1: Install Dart

If you haven’t already, install Dart on your system.

### 🪟 Windows / 🐧 Linux / 🍎 macOS
```bash
# Check if Dart is installed
dart --version

# If not installed, visit:
https://dart.dev/get-dart
```

---

## 📝 Step 2: Create a Dart File

Create a new file named **`hello.dart`** anywhere on your computer.

```bash
touch hello.dart
```

---

## 💻 Step 3: Write the Code

Open `hello.dart` in your code editor and add:

```dart
void main() {
  print('Hello, World!');
}
```

### Explanation:
- `void main()` → The entry point of every Dart program.  
- `print()` → A built-in function to display text on the screen.  
- `'Hello, World!'` → A string (text) enclosed in single quotes.

---

## ▶️ Step 4: Run the Program

Run your program in the terminal:

```bash
dart run hello.dart
```

You’ll see this output:

```
Hello, World!
```

---

## 🧩 Step 5: Try Modifying It

Experiment by changing the text:

```dart
void main() {
  print('Welcome to Dart!');
}
```

Then run it again to see the result.

---

## ✅ Summary

| Concept | Description |
|----------|--------------|
| `main()` | Starting point of the program |
| `print()` | Outputs text to the console |
| `'...'` | String literal (text) |

---

### 🎯 You Learned:
- How to write and run your first Dart program.  
- The basic structure of a Dart program.  
- How output is displayed in the console.

Next → [Variables and Data Types](variables.md)
