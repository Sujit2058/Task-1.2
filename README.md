# Inventory MAnagement App – Debugging and UI Optimization (Flutter)

## 📌 Project Overview
This task focuses on debugging and improving a Flutter-based **Product Inventory Manager** application.  
The original prototype contained multiple issues related to **layout rendering**, **asynchronous state handling**, and **UI/UX structure**, which caused crashes and logical inconsistencies.

The goal of Task 1.2 is to make the app **stable, functional, and visually improved** by following Flutter best practices.

---

## 🎯 Objectives
- Fix render engine crashes
- Ensure safe asynchronous operations
- Improve UI/UX and layout structure
- Fix logical issues in restocking functionality
- Maintain clean and readable code

---

## ❌ Issues in the Original Code

### 1. Render Engine Crash
- `ListView.builder` was placed inside a `Row` without height constraints
- This caused a **RenderFlex overflow error**
- Flutter requires scrollable widgets to have bounded dimensions

---

### 2. Unsafe Asynchronous State Update
- `Future.delayed()` was used before calling `setState()`
- If the user left the screen during the delay, `setState()` was called on a disposed widget
- This resulted in a runtime crash

---

### 3. Logical Flaw in Restocking
- `isUpdating` variable was declared but not used
- Users could tap the **Restock** button multiple times
- This caused incorrect inventory updates

---

### 4. Poor UI/UX
- No padding or spacing
- Weak visual hierarchy
- Not aligned with Material Design guidelines

---

## ✅ Solutions Implemented

### ✔ Layout Fix
- Replaced `Row` with `Column`
- Wrapped `ListView.builder` with `Expanded` to provide height constraints

---

### ✔ Async Safety
- Added `mounted` check before calling `setState()`
- Prevented crashes when navigating away during async operations

---

### ✔ Logical Consistency
- Properly used `isUpdating` flag
- Disabled restock button during update
- Prevented multiple restock calls

---

### ✔ UI / UX Improvements
- Added padding and spacing
- Used `Card` and improved typography
- Created a cleaner and more professional UI

---

## 🛠 Technologies Used
- Flutter
- Dart
- Material Design

---

## 📂 File Information
- **Task File:** `main_2.dart`
- **Task Number:** 1.2

---

## 🧠 Key Learning Outcome
> Most Flutter crashes occur due to unbounded layouts and unsafe asynchronous `setState()` calls.  
> Proper layout constraints and lifecycle checks are essential for stable apps.

---

## ✅ Final Result
- App runs without crashes
- Inventory updates correctly
- Safe async behavior
- Improved UI and user experience

---

## ✍️ Author
**Sujit Prajapati**
