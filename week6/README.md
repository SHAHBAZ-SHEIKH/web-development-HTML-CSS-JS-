# 📘 JavaScript Concepts: Objects, Arrays, Reduce, LocalStorage & `this` Keyword

This document explains **Objects**, **Array of Objects**, important **Array Methods**, **Local Storage**, and the **`this` keyword** in JavaScript with definitions and examples.

---

## 🔹 What is an Object?

An **Object** is a collection of **key-value pairs**.
It helps us store related data together.

✅ Example:

```javascript
const student = {
  name: "Ali",
  age: 20,
  isEnrolled: true,
  courses: ["Math", "Science", "English"], // Array inside object
  address: { city: "Karachi", country: "Pakistan" }, // Object inside object
  greet: function() {                       // Function inside object
    return `Hello, my name is ${this.name}`;
  }
};

console.log(student.name);         // Ali
console.log(student.courses[1]);   // Science
console.log(student.address.city); // Karachi
console.log(student.greet());      // Hello, my name is Ali
```

👉 Inside an object, we can store:

* String
* Number
* Boolean
* Array
* Another Object
* Function

---

## 🔹 Array of Objects

Used when we want to store multiple objects together in a list.
Very useful in real-world apps like **users, products, students, tasks**.

✅ Example:

```javascript
const students = [
  { id: 1, name: "Ali", age: 20 },
  { id: 2, name: "Sara", age: 22 },
  { id: 3, name: "Ahmed", age: 19 }
];

console.log(students[0].name); // Ali
console.log(students[2].age);  // 19
```

---

## 🔹 Array Methods

### 1️⃣ forEach()

Executes a function once for each array element.
Used for iteration (does not return a new array).

```javascript
const numbers = [1, 2, 3, 4];
numbers.forEach(num => console.log(num * 2));
// Output: 2, 4, 6, 8
```

With Array of Objects:

```javascript
students.forEach(student => {
  console.log(student.name);
});
// Output: Ali, Sara, Ahmed
```

---

### 2️⃣ map()

Creates a **new array** by applying a function to each element.
Used when transforming data.

```javascript
const numbers = [1, 2, 3];
const squares = numbers.map(num => num * num);
console.log(squares); // [1, 4, 9]
```

With Array of Objects:

```javascript
const names = students.map(s => s.name);
console.log(names); // ["Ali", "Sara", "Ahmed"]
```

---

### 3️⃣ filter()

Creates a **new array** with elements that pass a condition.
Used for filtering data.

```javascript
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

With Array of Objects:

```javascript
const adults = students.filter(s => s.age > 20);
console.log(adults);
// [{ id: 2, name: "Sara", age: 22 }]
```

---

### 4️⃣ find()

Returns the **first element** that matches the condition.
Used when you need only **one specific item**.

```javascript
const firstEven = numbers.find(num => num % 2 === 0);
console.log(firstEven); // 2
```

With Array of Objects:

```javascript
const studentSara = students.find(s => s.name === "Sara");
console.log(studentSara);
// { id: 2, name: "Sara", age: 22 }
```

---

### 5️⃣ reduce()

Reduces an array to a **single value** (sum, average, max, etc.).

```javascript
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // 10
```

👉 Step by Step:

* Initial: acc = 0
* First iteration: 0 + 1 = 1
* Second: 1 + 2 = 3
* Third: 3 + 3 = 6
* Fourth: 6 + 4 = 10

With Array of Objects:

```javascript
const totalAge = students.reduce((acc, s) => acc + s.age, 0);
console.log(totalAge); // 61
```

---

## 🔹 Local Storage

Local Storage allows you to **store data in the browser permanently** (until manually cleared).

✅ Example:

```javascript
// Save data
localStorage.setItem("username", "Ali");

// Get data
console.log(localStorage.getItem("username")); // Ali

// Remove data
localStorage.removeItem("username");

// Clear all
localStorage.clear();
```

Storing Objects/Arrays:

```javascript
localStorage.setItem("students", JSON.stringify(students));

const savedStudents = JSON.parse(localStorage.getItem("students"));
console.log(savedStudents);
```

👉 Methods:

* `setItem(key, value)` → Store data
* `getItem(key)` → Retrieve data
* `removeItem(key)` → Remove specific data
* `clear()` → Remove all data
* `JSON.stringify()` → Convert object/array → string
* `JSON.parse()` → Convert string → object/array

---

## 🔹 The `this` Keyword

The `this` keyword refers to the **object that is currently executing the function**.

✅ Example 1 (Inside Object):

```javascript
const person = {
  name: "Ali",
  greet: function() {
    return `Hello, my name is ${this.name}`;
  }
};

console.log(person.greet()); // Hello, my name is Ali
```

✅ Example 2 (Global Context):

```javascript
console.log(this);
// In browser → Window object
```

✅ Example 3 (Function Context):

```javascript
function showThis() {
  console.log(this);
}
showThis();
// In strict mode → undefined
// In normal mode → Window object
```

👉 Summary:

* In an object method → `this` refers to the object itself.
* In a regular function → `this` refers to the global object (window in browsers).
* In strict mode → standalone functions return `undefined`.

---

## 🎯 Summary

* **Objects**: Store related data together.
* **Array of Objects**: Manage lists of objects.
* **forEach**: Loop through items.
* **map**: Transform data.
* **filter**: Extract data.
* **find**: Get one item.
* **reduce**: Combine into a single value.
* **Local Storage**: Save data in browser (with JSON).
* **this keyword**: Refers to the current object executing the function.

👉 With these concepts, you can build real-world apps like:

* E-commerce carts
* Student management systems
* Todo apps
* Weather apps
