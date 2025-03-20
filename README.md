# Kotlin Language Concepts

# 🚀 **Kotlin: `var` vs `val`**

In **Kotlin**, `var` and `val` are used to declare variables, but they differ in terms of **mutability**.

- **`var`** → Mutable (Can be changed)
- **`val`** → Immutable (Cannot be changed once assigned)

---

## ✅ **1. Key Differences Between `var` and `val`**

| Aspect         | `var` (Variable)                                   | `val` (Value)                                      |
|-----------------|---------------------------------------------------|-----------------------------------------------------|
| **Mutability**  | Mutable (Can be changed)                         | Immutable (Cannot be changed once assigned)        |
| **Reassignment**| Can be reassigned                               | Cannot be reassigned                               |
| **Use Case**    | Use when the value needs to change               | Use when the value remains constant               |
| **Compilation** | No compile-time error on reassignment            | Compile-time error on reassignment                |
| **Performance** | Slightly less performant (due to possible changes) | More performant for constants or fixed data       |

---

## ✅ **2. Examples**

### ➡️ **Using `var` (Mutable Variable)**
```kotlin
var name = "John"
println(name) // Output: John

name = "Doe"  // Can be reassigned
println(name) // Output: Doe
```

### ➡️ **Using `val` (Immutable Variable)**
```kotlin
val age = 25
println(age) // Output: 25

// age = 30  // Error: Val cannot be reassigned
```

---

## ✅ **3. When to Use `var` and `val`**

- **Use `val`** for constants, configuration values, or data that won't change.
- **Use `var`** for values that need to change, like counters, UI state, or user inputs.

### ➡️ **Example: Using `val` for Constants**
```kotlin
val pi = 3.14159
println("Value of pi: $pi")
```

### ➡️ **Example: Using `var` for Changing State**
```kotlin
var counter = 0
counter++
println("Counter: $counter")
```

---

## ✅ **4. Best Practices**
- Prefer using **`val`** over **`var`** for safer and more predictable code.
- Use **`var`** only when necessary for mutable states.
- Immutable variables (`val`) lead to fewer bugs and better performance.

---

## ✅ **Final Thoughts**
- **`val`** = Constant / Read-Only (like `final` in Java)
- **`var`** = Mutable / Changeable

---
---
---

# 🚀 **Kotlin `in` Operator**

The `in` operator in **Kotlin** is used to **check if a value exists within a range, collection, or any iterable object**. It can also be used for iteration in loops.

---

## ✅ **1. Using `in` for Range Checks**
You can check if a value lies within a range using the `in` operator.

### ➡️ **Example: Range Check**
```kotlin
val number = 7

if (number in 1..10) { // Checks if number is between 1 and 10
    println("$number is in the range")
} else {
    println("$number is not in the range")
}
```
**Output:**
```
7 is in the range
```

### ➡️ **Using `!in` to Check Not in Range**
```kotlin
val age = 25

if (age !in 18..30) {
    println("Age is not in the range")
} else {
    println("Age is in the range")
}
```
**Output:**
```
Age is in the range
```

---

## ✅ **2. Using `in` with Collections**
You can check whether a specific element exists in a collection like a list, set, or map.

### ➡️ **Example: Check in List**
```kotlin
val fruits = listOf("Apple", "Banana", "Mango")

if ("Mango" in fruits) {
    println("Mango is in the list")
} else {
    println("Mango is not in the list")
}
```
**Output:**
```
Mango is in the list
```

### ➡️ **Example: Check in Set**
```kotlin
val numbers = setOf(1, 2, 3, 4, 5)

if (6 !in numbers) {
    println("6 is not in the set")
}
```
**Output:**
```
6 is not in the set
```

---

## ✅ **3. Using `in` for Iteration**
The `in` operator is also used in `for` loops to iterate over a collection or range.

### ➡️ **Example: Loop Through a Range**
```kotlin
for (i in 1..5) {
    println("Number: $i")
}
```
**Output:**
```
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5
```

### ➡️ **Example: Loop Through a List**
```kotlin
val names = listOf("John", "Emma", "Sophia")
for (name in names) {
    println("Hello, $name!")
}
```
**Output:**
```
Hello, John!
Hello, Emma!
Hello, Sophia!
```

---

## ✅ **4. Using `in` with When Expression**
You can use `in` within a `when` expression for cleaner code.

### ➡️ **Example: Using `in` with When**
```kotlin
val score = 85

when (score) {
    in 90..100 -> println("Grade: A")
    in 80..89 -> println("Grade: B")
    in 70..79 -> println("Grade: C")
    else -> println("Grade: F")
}
```
**Output:**
```
Grade: B
```

---

## ✅ **Summary**
- `in` is used for **range checks** (`in 1..10`).
- `in` works for **collection checks** (`in listOf(...)`).
- `in` simplifies **loops and iterations**.
- `in` is useful with **when expressions** for clean code.

---
---
---
# 🚀 **Kotlin: Index Access Operator (`[]`)**

In **Kotlin**, the **index access operator** (`[]`) is used to access or modify elements of collections like **Lists**, **Arrays**, **Maps**, and custom classes that overload this operator.

---

## ✅ **1. Using Index Access with Arrays and Lists**

You can access and modify elements using their index.

### ➡️ **Example: Accessing Elements**
```kotlin
val numbers = arrayOf(10, 20, 30, 40)
println(numbers[2]) // Output: 30
```

### ➡️ **Example: Modifying Elements**
```kotlin
val mutableList = mutableListOf("Apple", "Banana", "Cherry")
mutableList[1] = "Blueberry" // Update Banana to Blueberry
println(mutableList) // Output: [Apple, Blueberry, Cherry]
```

---

## ✅ **2. Using Index Access with Maps**

You can use the index access operator to get or set values using keys.

### ➡️ **Example: Accessing Values by Key**
```kotlin
val map = mapOf("a" to 1, "b" to 2, "c" to 3)
println(map["b"]) // Output: 2
```

### ➡️ **Example: Modifying Values in Mutable Map**
```kotlin
val mutableMap = mutableMapOf("x" to 100, "y" to 200)
mutableMap["x"] = 500
println(mutableMap) // Output: {x=500, y=200}
```

---

## ✅ **3. Using Index Access with Custom Classes**

You can overload the index operator using the `get()` and `set()` functions.

### ➡️ **Example: Custom Class with Index Operator**
```kotlin
class CustomData(val data: MutableList<String>) {
    operator fun get(index: Int): String = data[index]
    operator fun set(index: Int, value: String) {
        data[index] = value
    }
}

val custom = CustomData(mutableListOf("A", "B", "C"))
println(custom[1]) // Output: B
custom[1] = "Z"
println(custom.data) // Output: [A, Z, C]
```

---

## ✅ **4. Error Handling with Index Access**
- Accessing an invalid index will throw an **IndexOutOfBoundsException**.
- Always ensure the index is within the bounds using `if` checks or using `getOrNull()`.

### ➡️ **Example: Safe Access with `getOrNull()`**
```kotlin
val list = listOf(1, 2, 3)
println(list.getOrNull(5) ?: "Index out of range") // Output: Index out of range
```

---

## ✅ **5. Summary**
- `[]` is used to **access or modify** elements by index.
- Works with **Lists**, **Arrays**, **Maps**, and **Custom Classes**.
- Supports operator overloading with `get()` and `set()`.
- Use `getOrNull()` for safer access.

