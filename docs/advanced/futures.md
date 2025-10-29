# ⏳ Dart Futures

A **Future** in Dart represents a **value that will be available later** — after some asynchronous operation completes.  
It’s the **building block** of asynchronous programming in Dart.

---

## 🧠 Why Futures?

Normally, Dart runs code **synchronously** (line by line).  
But some tasks — like reading a file or calling an API — take time.  
Instead of blocking, Dart uses **Futures** to handle these operations asynchronously.

---

## 🔍 What Is a Future?

A **Future** is like a *promise* that returns:
- A **value** when the operation succeeds  
- An **error** if something goes wrong  

Example:

```dart
Future<String> fetchUserName() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Arshad';
}

void main() async {
  print('Fetching...');
  String name = await fetchUserName();
  print('Hello, $name!');
}
```

🕒 Output:
```
Fetching...
Hello, Arshad!
```

---

## ⚙️ Creating Futures

There are several ways to create a `Future`:

| Type | Example |
|------|----------|
| Immediate value | `Future.value(10)` |
| With delay | `Future.delayed(Duration(seconds: 2), () => 42)` |
| From async function | `Future<int> getData() async => 123;` |
| With computation | `Future(() => heavyCalculation())` |

Example:

```dart
Future<int> square(int n) async {
  return n * n;
}

void main() async {
  print(await square(4)); // 16
}
```

---

## 🧩 Using `.then()`, `.catchError()`, `.whenComplete()`

Before `async/await`, Futures used **callback chaining**:

```dart
Future<int> getNumber() => Future.delayed(Duration(seconds: 1), () => 5);

void main() {
  getNumber()
    .then((value) => print('Value: $value'))
    .catchError((error) => print('Error: $error'))
    .whenComplete(() => print('Done!'));
}
```

🧾 Output:
```
Value: 5
Done!
```

✅ Works fine — but `async/await` is much cleaner.

---

## ✨ Using `async` and `await`

You can write asynchronous code **like synchronous code** using `async` and `await`:

```dart
Future<String> getData() async {
  await Future.delayed(Duration(seconds: 1));
  return 'Data loaded';
}

void main() async {
  print('Waiting...');
  var data = await getData();
  print(data);
}
```

Output:
```
Waiting...
Data loaded
```

---

## 🚨 Handling Errors

Use `try` / `catch` inside `async` functions:

```dart
Future<String> riskyOperation() async {
  throw Exception('Something went wrong!');
}

void main() async {
  try {
    var result = await riskyOperation();
    print(result);
  } catch (e) {
    print('Caught error: $e');
  } finally {
    print('Operation complete.');
  }
}
```

Output:
```
Caught error: Exception: Something went wrong!
Operation complete.
```

---

## ⏲️ Running Multiple Futures

You can run multiple async tasks **at the same time**:

### 1️⃣ Using `Future.wait()`
Waits for all futures to complete.

```dart
void main() async {
  var results = await Future.wait([
    Future.delayed(Duration(seconds: 1), () => 'Task 1'),
    Future.delayed(Duration(seconds: 2), () => 'Task 2'),
  ]);
  print(results); // [Task 1, Task 2]
}
```

### 2️⃣ Using `Future.any()`
Returns the **first** future that completes.

```dart
void main() async {
  var result = await Future.any([
    Future.delayed(Duration(seconds: 2), () => 'Slow'),
    Future.delayed(Duration(seconds: 1), () => 'Fast'),
  ]);
  print(result); // Fast
}
```

---

## 🧱 Common Future Methods

| Method | Description | Example |
|--------|--------------|----------|
| `.then()` | Run code after completion | `future.then(print)` |
| `.catchError()` | Handle errors | `future.catchError(print)` |
| `.whenComplete()` | Always run at end | `future.whenComplete(() => print('done'))` |
| `Future.wait()` | Wait for many | `await Future.wait([...])` |
| `Future.any()` | Take first result | `await Future.any([...])` |

---

## 🧮 Future vs Stream

| Feature | Future | Stream |
|----------|---------|--------|
| Returns | One value | Many values |
| Completion | Ends after one result | Ends after many events |
| Use case | Fetch data once | Continuous data flow |
| Example | HTTP request | WebSocket messages |

---

## 🏁 Summary

| Concept | Key Idea |
|----------|-----------|
| **Future** | Represents a single async result |
| **async / await** | Simplifies async code |
| **Error handling** | `try / catch / finally` |
| **Parallel tasks** | `Future.wait()` & `Future.any()` |
| **Streams** | For multiple async values |

---

## 🎯 Quick Practice

Write a function that simulates downloading two files, then prints “All downloads done!” when both complete.

```dart
Future<void> download(String file) async {
  print('Downloading $file...');
  await Future.delayed(Duration(seconds: 2));
  print('$file downloaded!');
}

void main() async {
  await Future.wait([
    download('file1.txt'),
    download('file2.txt'),
  ]);
  print('All downloads done!');
}
```

Output:
```
Downloading file1.txt...
Downloading file2.txt...
file1.txt downloaded!
file2.txt downloaded!
All downloads done!
```

---

✅ **You’ve learned:**
- What Futures are and how they work  
- How to create, await, and handle errors  
- How to combine multiple async tasks  
- Difference between Futures and Streams  

Next → Learn **how Streams build on Futures** to handle *continuous asynchronous data*.
