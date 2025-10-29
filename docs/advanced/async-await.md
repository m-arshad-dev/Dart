# ⏳ Async and Await in Dart

In Dart, **`async`** and **`await`** make it easy to write **asynchronous** (non-blocking) code — especially when working with APIs, files, or delays.

---

## 🧠 What is Asynchronous Programming?

Normally, Dart executes code **line by line** (synchronously).  
But some operations take time (like reading a file or fetching data from the internet).  
We don’t want to block the program while waiting for them — that’s where **asynchronous code** helps.

---

## 🔹 The `Future` Type

A **`Future`** represents a value that **will be available later**.

Example:

```dart
Future<String> getData() {
  return Future.delayed(Duration(seconds: 2), () => 'Hello from Future!');
}
```

This function doesn’t return the string immediately.  
It returns a `Future` that completes **after 2 seconds**.

---

## 🔹 Using `then()`

Before learning `await`, let’s see how to handle Futures with `.then()`:

```dart
void main() {
  getData().then((value) {
    print(value);
  });

  print('Fetching data...');
}
```

**Output:**
```
Fetching data...
Hello from Future!
```

The program doesn’t wait — it continues executing.

---

## ⚙️ Using `async` and `await`

The `async` keyword tells Dart that a function is **asynchronous**,  
and `await` tells it to **pause** until the Future completes.

```dart
Future<void> main() async {
  print('Fetching data...');
  String data = await getData();
  print(data);
}
```

**Output:**
```
Fetching data...
Hello from Future!
```

Now the program **waits** at `await getData()` until the Future completes —  
but **only this async function** pauses, not the whole app.

---

## ⚡ Async Function Rules

1. Add `async` after the function signature.
2. Use `await` **only inside** an `async` function.
3. `async` functions always return a `Future`, even if you return a simple value.

Example:

```dart
Future<int> addAsync(int a, int b) async {
  return a + b;
}
```

---

## 🚨 Error Handling with `try / catch`

When using `await`, wrap calls in `try`–`catch` to handle errors.

```dart
Future<void> main() async {
  try {
    String data = await fetchUserData();
    print(data);
  } catch (e) {
    print('Error: $e');
  }
}

Future<String> fetchUserData() async {
  throw Exception('Network error');
}
```

**Output:**
```
Error: Exception: Network error
```

---

## 🔁 Multiple Awaits

You can `await` multiple async calls sequentially:

```dart
Future<void> main() async {
  String user = await getUser();
  String posts = await getPosts();
  print('$user -> $posts');
}
```

Or run them **in parallel** with `Future.wait()`:

```dart
Future<void> main() async {
  var results = await Future.wait([getUser(), getPosts()]);
  print(results); // ['User data', 'Post data']
}
```

---

## ✅ Summary

| Concept | Description |
|----------|--------------|
| `Future` | Represents a value that will be available later |
| `async` | Marks a function as asynchronous |
| `await` | Waits for a Future to complete |
| `try/catch` | Handles async errors safely |
| `Future.wait()` | Runs multiple Futures in parallel |

---

## 🧩 Quick Practice

```dart
Future<String> downloadFile() async {
  await Future.delayed(Duration(seconds: 1));
  return 'File downloaded!';
}

Future<void> main() async {
  print('Starting...');
  print(await downloadFile());
  print('Done!');
}
```

**Expected Output:**
```
Starting...
File downloaded!
Done!
```

---

> 🏁 You’ve mastered the basics of asynchronous programming in Dart!  
> Next: learn about **Streams** for handling continuous async data.
