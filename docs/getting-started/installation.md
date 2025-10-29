# 💻 Step 2: Set Up Your Environment

Before you start coding in Dart, you need a place to write and run your programs.  
You can either use an **online editor (DartPad)** or install Dart **locally** on your computer.

---

## 💡 Option 1 — Use DartPad (Recommended for Beginners)

[DartPad](https://dartpad.dev) is an **online Dart editor** that lets you write, run, and share Dart code instantly — no installation required.

---

### 🪜 Step-by-Step Guide

#### 1️⃣ Open DartPad
Visit 👉 [https://dartpad.dev](https://dartpad.dev)

#### 2️⃣ Explore the Interface

- **Left panel** → Code editor (write your Dart code here)  
- **Right panel** → Console output (see your results here)  
- **Top bar** → Common actions:  
  - ▶️ **Run** — Execute your program  
  - 🔄 **Reset** — Restore the default example  
  - 💾 **Share** — Generate a shareable link to your code  

#### 3️⃣ Run Your First Program

DartPad loads a sample “Hello World” program by default:

```dart
void main() {
  print('Hello, World!');
}
```

Click **▶️ Run**, and you’ll see the output on the right:

```
Hello, World!
```

#### 4️⃣ Try Editing

Change the code to:

```dart
void main() {
  print('Welcome to Dart!');
}
```

Click **Run** again — your new message will appear.

#### 5️⃣ Experiment!

* DartPad supports **Dart basics**, **functions**, and even **Flutter UI code**
  (use **New Pad → Flutter** to try UI examples).
* You can use DartPad from any browser — no setup needed.

---

!!! success "You’re ready!"
✅ That’s it — you’re now ready to start coding in Dart *online*, instantly.

---

## 💻 Option 2 — Install Dart Locally (Recommended for Advanced Users)

If you want to build real Dart or Flutter projects, install Dart on your local machine.
This gives you **offline access**, **package management**, and **development tools**.

---

### 🪜 Step-by-Step Setup

### 1️⃣ Check System Requirements

You can install Dart on:

* 🪟 **Windows**
* 🐧 **Linux (Debian/Ubuntu-based)**
* 🍎 **macOS**

---

## 🐧 Installing Dart on Debian 13 (Trixie)

!!! info "Note"
🧠 Debian 13 uses updated package security — the old `apt-key` method is deprecated.  
Follow these new, secure steps to install the Dart SDK.

### Step 1 — Update Your System

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install apt-transport-https curl gnupg -y
```

---

### Step 2 — Add the Google Linux Repository Key

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://dl-ssl.google.com/linux/linux_signing_key.pub \
  | sudo gpg --dearmor -o /etc/apt/keyrings/dart.gpg
```

---

### Step 3 — Add the Dart Repository

```bash
echo "deb [signed-by=/etc/apt/keyrings/dart.gpg] \
https://storage.googleapis.com/download.dartlang.org/linux/debian stable main" \
| sudo tee /etc/apt/sources.list.d/dart_stable.list
```

---

### Step 4 — Install Dart SDK

```bash
sudo apt update
sudo apt install dart -y
```

---

### Step 5 — Verify Installation

```bash
dart --version
```

Expected output:

```
Dart SDK version: 3.x.x (stable)
```

---

### (Optional) Step 6 — Add Dart to PATH

If Dart isn’t recognized globally:

```bash
echo 'export PATH="$PATH:/usr/lib/dart/bin"' >> ~/.bashrc
source ~/.bashrc
```

---

### Step 7 — Test Your Setup

Create and run a test file:

```bash
mkdir ~/dart_projects
cd ~/dart_projects
nano hello.dart
```

Add the following code:

```dart
void main() {
  print('Hello, Debian 13! Dart is working perfectly.');
}
```

Run it:

```bash
dart run hello.dart
```

You should see:

```
Hello, Debian 13! Dart is working perfectly.
```

!!! success "Success"
✅ Dart SDK is now fully installed and configured on Debian 13 (Trixie).

---

## 🪟 Installing Dart on Windows

1. Visit 👉 [https://dart.dev/get-dart](https://dart.dev/get-dart)  
2. Download the **Windows Installer (.msi)**.  
3. Run it and follow the setup wizard.  
4. After installation, open **Command Prompt** and verify:

   ```bash
   dart --version
   ```

Expected output:

```
Dart SDK version: 3.x.x
```

---

## 🍎 Installing Dart on macOS

Install Dart using **Homebrew**:

```bash
brew tap dart-lang/dart
brew install dart
```

Then verify:

```bash
dart --version
```

---

## ⚙️ Set Up Your Code Editor

### 🧩 Using VS Code (Recommended)

1. Download → [https://code.visualstudio.com](https://code.visualstudio.com)  
2. Open VS Code → **Extensions** panel  
3. Search for **“Dart”** → Click **Install**

You can now create, run, and debug Dart projects inside VS Code.

!!! tip
💡 Other supported editors include **IntelliJ IDEA**, **Android Studio**, and **Sublime Text**.

---

## 🧪 Run Your First Local Program

1. Create a new directory and file:

   ```bash
   mkdir dart_projects
   cd dart_projects
   nano hello.dart
   ```

2. Add this code:

   ```dart
   void main() {
     print('Hello from Dart on your computer!');
   }
   ```

3. Run it:

   ```bash
   dart run hello.dart
   ```

Expected output:

```
Hello from Dart on your computer!
```

---

!!! success "All Set!"
✅ You’re now ready to build and run Dart projects locally.

Continue to:  
👉 **[Step 3: Your First Dart Program – Explained](../getting-started/hello-world.md)**  
to understand how `void main()` and `print()` work.

---

