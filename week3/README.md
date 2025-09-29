# 📦 JavaScript Arrays

## 📌 What is an Array?

An **Array** is a special variable that can hold **multiple values** at the same time.
Instead of creating separate variables for each value, arrays help us group them together.

👉 Example without array:

```js
let student1 = "Ali";
let student2 = "Sara";
let student3 = "Ahmed";
```

👉 Example with array:

```js
let students = ["Ali", "Sara", "Ahmed"];
console.log(students[0]); // Ali
console.log(students[2]); // Ahmed
```

🔑 **Array Indexing**:

* First element starts at **index 0**
* Last element is at **index length-1**

---

## 🔹 Why use Arrays?

* To **store multiple values** in a single variable.
* To **loop through data easily**.
* To **apply powerful built-in methods** like add, remove, search, merge, etc.

Example:

```js
let fruits = ["Apple", "Banana", "Mango"];
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

---

## 📊 Important Array Methods

### 1) **push()** → Add element at the end ✅ Modifies array

```js
let fruits = ["Apple", "Banana"];
fruits.push("Mango");
console.log(fruits); // ["Apple", "Banana", "Mango"]
```

---

### 2) **pop()** → Remove last element ✅ Modifies array

```js
let fruits = ["Apple", "Banana", "Mango"];
fruits.pop();
console.log(fruits); // ["Apple", "Banana"]
```

---

### 3) **unshift()** → Add element at the beginning ✅ Modifies array

```js
let fruits = ["Banana", "Mango"];
fruits.unshift("Apple");
console.log(fruits); // ["Apple", "Banana", "Mango"]
```

---

### 4) **shift()** → Remove first element ✅ Modifies array

```js
let fruits = ["Apple", "Banana", "Mango"];
fruits.shift();
console.log(fruits); // ["Banana", "Mango"]
```

---

### 5) **splice(start, deleteCount, newItems)** → Add/Remove elements ✅ Modifies array

```js
let fruits = ["Apple", "Banana", "Cherry"];
fruits.splice(1, 1, "Mango");  
console.log(fruits); // ["Apple", "Mango", "Cherry"]
```

---

### 6) **slice(start, end)** → Extract part of array ❌ Does not modify

```js
let fruits = ["Apple", "Banana", "Cherry", "Mango"];
console.log(fruits.slice(1, 3)); // ["Banana","Cherry"]
```

---

### 7) **indexOf(value)** → Find first index ❌ Does not modify

```js
let nums = [10, 20, 30, 40];
console.log(nums.indexOf(30)); // 2
```

---

### 8) **includes(value)** → Check if exists ❌ Does not modify

```js
let nums = [10, 20, 30, 40];
console.log(nums.includes(20)); // true
console.log(nums.includes(50)); // false
```

---

## 📋 Quick Table – Modify vs Not Modify

| Method     | Modifies Array | Returns              |
| ---------- | -------------- | -------------------- |
| push()     | ✅ Yes          | New length           |
| pop()      | ✅ Yes          | Removed element      |
| unshift()  | ✅ Yes          | New length           |
| shift()    | ✅ Yes          | Removed element      |
| splice()   | ✅ Yes          | Removed part         |
| slice()    | ❌ No           | New array            |
| indexOf()  | ❌ No           | Index (number)       |
| includes() | ❌ No           | Boolean (true/false) |

---

## 🎯 Challenges

1️⃣ Create an array of 5 numbers. Add a new number at the end using `push()`.
2️⃣ Remove the last number using `pop()`.
3️⃣ Add a new fruit at the beginning of an array using `unshift()`.
4️⃣ Extract the middle two elements using `slice()`.
5️⃣ Check if `"Mango"` exists in the fruits array using `includes()`.

---

## 📝 Assignment (Arrays + Previous Topics)

1. Make an array of 5 friends’ names → remove the last one and add `"New Friend"`.
2. Ask user for 3 numbers, store them in an array, and print the sum.
3. Replace `"Banana"` with `"Grapes"` in `["Apple","Banana","Cherry"]`.
4. Merge two arrays `[1,2,3]` and `[4,5,6]`.
5. Search for `"Ali"` in an array of names and print whether found or not.

---

## 💡 Motivation Quote

*"An array in JavaScript is like a box with many sections — the more you explore, the easier it gets to organize your knowledge."* 🚀
