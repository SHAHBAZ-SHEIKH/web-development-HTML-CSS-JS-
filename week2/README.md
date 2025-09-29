# 📝 JavaScript Strings

## 📌 What is a String?

A **string** is a sequence of characters enclosed in single (`' '`), double (`" "`), or backticks (`` ` ` ``).

👉 Example:

```js
let name1 = "Shahbaz";   // double quotes
let name2 = 'Ahmed';     // single quotes
let greeting = `Hello ${name1}`; // template literal
```

---

## 🔹 Why use Strings?

* To store and work with text.
* To display messages, names, user input, etc.
* To perform operations like search, replace, split, etc.

---

## 📊 Important String Methods

### 1) **length** → Find string length ❌ Does not modify

```js
let text = "Hello World";
console.log(text.length); // 11
```

---

### 2) **toUpperCase() / toLowerCase()** → Change case ❌ Does not modify

```js
let word = "JavaScript";
console.log(word.toUpperCase()); // JAVASCRIPT
console.log(word.toLowerCase()); // javascript
```

---

### 3) **charAt(index)** → Get character ❌ Does not modify

```js
let text = "Hello";
console.log(text.charAt(0)); // H
console.log(text.charAt(4)); // o
```

---

### 4) **indexOf(substring) / lastIndexOf(substring)** → Find position ❌ Does not modify

```js
let text = "I love JavaScript, JavaScript is fun!";
console.log(text.indexOf("JavaScript"));     // 7
console.log(text.lastIndexOf("JavaScript")); // 19
```

---

### 5) **includes(substring)** → Check existence ❌ Does not modify

```js
let text = "Hello World";
console.log(text.includes("World")); // true
console.log(text.includes("JS"));    // false
```

---

### 6) **slice(start, end)** → Extract part ❌ Does not modify

```js
let text = "Hello World";
console.log(text.slice(0, 5)); // Hello
console.log(text.slice(6));    // World
```

---

### 7) **substring(start, end)** → Similar to slice but no negative index ❌ Does not modify

```js
let text = "Hello World";
console.log(text.substring(0, 5)); // Hello
```

---

### 8) **replace(old, new)** → Replace substring ❌ Does not modify

```js
let text = "I love JavaScript";
console.log(text.replace("JavaScript", "Python")); 
// I love Python
```

---

### 9) **trim()** → Remove spaces from both ends ❌ Does not modify

```js
let text = "   Hello JS   ";
console.log(text.trim()); // Hello JS
```

---

### 🔟 **split(separator)** → Convert string into array ❌ Does not modify

```js
let text = "Apple, Banana, Mango";
let arr = text.split(", ");
console.log(arr); // ["Apple","Banana","Mango"]
```

---

## 📋 Quick Table – Modify vs Not Modify

| Method        | Modifies String | Returns              |
| ------------- | --------------- | -------------------- |
| length        | ❌ No            | Number               |
| toUpperCase() | ❌ No            | New string           |
| toLowerCase() | ❌ No            | New string           |
| charAt()      | ❌ No            | Character            |
| indexOf()     | ❌ No            | Number (position)    |
| lastIndexOf() | ❌ No            | Number (position)    |
| includes()    | ❌ No            | Boolean (true/false) |
| slice()       | ❌ No            | New string           |
| substring()   | ❌ No            | New string           |
| replace()     | ❌ No            | New string           |
| trim()        | ❌ No            | New string           |
| split()       | ❌ No            | Array                |

---

## 🎯 Challenges

1️⃣ Create a string `"   JavaScript is fun   "` → Trim spaces and convert to uppercase.
2️⃣ Take a string `"Hello World"` → Extract only `"World"` using `slice()`.
3️⃣ Replace `"bad"` with `"good"` in `"JS is bad"` using `replace()`.
4️⃣ Check if `"JS"` exists in `"I love JS"` using `includes()`.
5️⃣ Convert `"Ali, Sara, Ahmed"` into an array of names using `split()`.

---

## 📝 Assignment (Strings + Previous Topics)

1. Make a string `"Hello Students"` → print its length.
2. Take user input name → print it in uppercase.
3. Search for `"apple"` in `"I like apple pie"` and print position.
4. Replace `"World"` with `"JS"` in `"Hello World"`.
5. Take a sentence and split it into words.

---

## 💡 Motivation Quote

*"Strings are like words of your code — the better you master them, the better story your program tells."* ✨
