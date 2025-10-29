# 🧺 Dart Collections

Collections in Dart are used to store and manage groups of objects.  
The main types are:

- **List** → ordered, indexed collection  
- **Set** → unordered, unique items  
- **Map** → key-value pairs  
- **Queue** → double-ended structure (from `dart:collection`)

---

## 📋 1. Lists

A **List** is an ordered collection of items (like arrays in other languages).

```dart
void main() {
  // Fixed-length list
  var fixedList = List<int>.filled(3, 0);
  fixedList[0] = 10;

  // Growable list
  var numbers = [1, 2, 3];
  numbers.add(4);
  numbers.remove(2);
  
  print(numbers); // [1, 3, 4]
  print(numbers.length); // 3
}
```

### Common List Methods
| Method | Description |
|--------|--------------|
| `add(value)` | Add single element |
| `addAll([...])` | Add multiple elements |
| `remove(value)` | Remove by value |
| `removeAt(index)` | Remove by index |
| `contains(value)` | Check if value exists |
| `sort()` | Sort elements |
| `reversed` | Reverse order |

---

## 🧩 2. Sets

A **Set** stores **unique** values and has **no index**.

```dart
void main() {
  var fruits = {'apple', 'banana', 'orange'};
  fruits.add('banana'); // duplicate ignored
  fruits.remove('apple');

  print(fruits); // {banana, orange}
  print(fruits.contains('orange')); // true
}
```

### Common Set Methods
| Method | Description |
|--------|--------------|
| `add(value)` | Add single item |
| `remove(value)` | Remove item |
| `contains(value)` | Check existence |
| `union(otherSet)` | Combine sets |
| `intersection(otherSet)` | Common items |
| `difference(otherSet)` | Unique items in current set |

---

## 🗺️ 3. Maps

A **Map** stores key–value pairs.  
Keys must be unique; values can repeat.

```dart
void main() {
  var user = {
    'name': 'Arshad',
    'age': 22,
    'country': 'Pakistan'
  };

  user['email'] = 'arshad@example.com';
  user.remove('age');

  print(user['name']); // Arshad
  print(user.keys); // (name, country, email)
  print(user.values); // (Arshad, Pakistan, arshad@example.com)
}
```

### Common Map Methods
| Method | Description |
|--------|--------------|
| `keys` / `values` | Return all keys or values |
| `addAll({...})` | Add multiple pairs |
| `remove(key)` | Remove entry by key |
| `containsKey(key)` | Check if key exists |
| `forEach((k, v) {})` | Loop through entries |

---

## 🔁 4. Queues

A **Queue** allows adding/removing items from **both ends**.  
You need to import it:

```dart
import 'dart:collection';

void main() {
  Queue<String> queue = Queue.from(['A', 'B', 'C']);
  
  queue.addFirst('Start');
  queue.addLast('End');
  queue.removeFirst();

  print(queue); // (B, C, End)
}
```

### Common Queue Methods
| Method | Description |
|--------|--------------|
| `add(value)` / `addAll([...])` | Add at end |
| `addFirst(value)` | Add at start |
| `addLast(value)` | Add at end |
| `removeFirst()` / `removeLast()` | Remove from start/end |
| `clear()` | Remove all elements |

---

## 🧠 Bonus: Collection Operations

Dart collections support **functional-style methods** like:

```dart
void main() {
  var numbers = [1, 2, 3, 4, 5];

  var doubled = numbers.map((n) => n * 2);
  var evens = numbers.where((n) => n.isEven);
  var sum = numbers.reduce((a, b) => a + b);

  print(doubled.toList()); // [2, 4, 6, 8, 10]
  print(evens.toList()); // [2, 4]
  print(sum); // 15
}
```

### Useful Methods
| Method | Description |
|--------|--------------|
| `map()` | Transform each element |
| `where()` | Filter elements |
| `reduce()` | Combine into one value |
| `any()` / `every()` | Test conditions |
| `forEach()` | Loop over collection |

---

## ✅ Summary

| Type | Ordered | Unique | Key–Value | Import Needed |
|------|----------|---------|------------|----------------|
| **List** | ✅ | ❌ | ❌ | No |
| **Set** | ❌ | ✅ | ❌ | No |
| **Map** | ❌ | ✅ (keys) | ✅ | No |
| **Queue** | ✅ | ❌ | ❌ | ✅ (`dart:collection`) |

---

🎯 **Next Step:**  
Try practicing by building small programs that use these collections — like:
- A todo list (using `List`)
- A contact book (using `Map`)
- A unique tag system (using `Set`)
- A task processor (using `Queue`)
