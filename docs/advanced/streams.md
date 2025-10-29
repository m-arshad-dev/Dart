# 💧 Dart Streams

Streams in Dart are used to handle **asynchronous data** — values that arrive **over time**.  
They’re like “pipes” that deliver data chunks (events) one after another.

---

## 🧠 Why Streams?

- Use **`Future`** for a *single* async value.  
- Use **`Stream`** for *multiple* async values.

👉 Example: Reading user input, listening to file downloads, or receiving messages from a server.

---

## 🧩 Stream Basics

A stream delivers:
- **Data events** → actual values
- **Error events** → exceptions
- **Done event** → when no more data will come

Example:

```dart
Stream<int> numberStream() async* {
  for (int i = 1; i <= 3; i++) {
    await Future.delayed(Duration(seconds: 1));
    yield i;
  }
}

void main() async {
  await for (var num in numberStream()) {
    print('Received: $num');
  }
}
```

📤 Output:
```
Received: 1
Received: 2
Received: 3
```

---

## ⚙️ Stream Types

| Type | Description |
|------|--------------|
| **Single-subscription Stream** | Listened to only once (default) |
| **Broadcast Stream** | Can have multiple listeners |

Example:

```dart
var stream = Stream<int>.periodic(
  Duration(seconds: 1),
  (count) => count,
).take(3);

stream.listen((value) => print('First: $value'));
stream.listen((value) => print('Second: $value')); // ❌ Error (single)
```

✅ Fix with broadcast:
```dart
var broadcast = stream.asBroadcastStream();
broadcast.listen((v) => print('First: $v'));
broadcast.listen((v) => print('Second: $v'));
```

---

## 🔄 StreamController

You can create custom streams using **`StreamController`**.

```dart
import 'dart:async';

void main() {
  final controller = StreamController<String>();

  controller.stream.listen(
    (data) => print('Data: $data'),
    onError: (err) => print('Error: $err'),
    onDone: () => print('Stream closed'),
  );

  controller.add('Hello');
  controller.add('World');
  controller.addError('Oops!');
  controller.close();
}
```

---

## 🧱 Stream Operations

Streams have powerful methods to transform data:

| Method | Example |
|--------|----------|
| `map()` | `stream.map((e) => e * 2)` |
| `where()` | `stream.where((e) => e.isEven)` |
| `take(n)` | `stream.take(3)` |
| `skip(n)` | `stream.skip(2)` |
| `toList()` | `await stream.toList()` |

Example:

```dart
final stream = Stream.fromIterable([1, 2, 3, 4, 5]);

await for (var n in stream.where((n) => n.isEven).map((n) => n * 10)) {
  print(n);
}
```

Output:
```
20
40
```

---

## 🧰 Common Stream Sources

| Use Case | Example |
|-----------|----------|
| From list | `Stream.fromIterable([1,2,3])` |
| Periodic | `Stream.periodic(Duration(seconds: 1), (count) => count)` |
| Controller | `StreamController()` |
| Async generator | `async*` with `yield` |

---

## 🧩 Combining Streams

You can merge or transform streams using packages like **`rxdart`**:

```dart
import 'package:rxdart/rxdart.dart';

void main() {
  final s1 = Stream.value(1);
  final s2 = Stream.value(2);

  Rx.merge([s1, s2]).listen(print); // 1, 2
}
```

---

## 🏁 Summary

| Concept | Key Idea |
|----------|-----------|
| **Stream** | Asynchronous sequence of events |
| **StreamController** | Manually manage stream data |
| **await for** | Asynchronously consume stream data |
| **Broadcast Stream** | Multiple listeners |
| **Transformations** | Use `map`, `where`, etc. |

---

## 🎯 Quick Practice

Create a stream that emits numbers from 1–5 every second, doubles them, and stops when done.

```dart
Stream<int> doubledNumbers() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(Duration(seconds: 1));
    yield i * 2;
  }
}

void main() async {
  await for (var num in doubledNumbers()) {
    print(num);
  }
}
```

Output:
```
2
4
6
8
10
```

---

✅ **You’ve learned:**
- What streams are and why they’re useful  
- How to create, listen, and transform them  
- How to use `StreamController` and broadcast streams  

Next up → Learn about **Futures vs Streams** and how to integrate both efficiently.
