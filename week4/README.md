# Week 3 - Loops in JavaScript

In programming, loops are used to repeat actions without writing the same code multiple times.
They help us save time, reduce errors, and make the code cleaner.

---

## 1. `for` Loop

The **for loop** is mostly used when we know how many times we want to repeat something.

### Example 1: Print numbers 1 to 5

```javascript
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

**Output:**

```
1
2
3
4
5
```

---

### Example 2: Print even numbers between 1 to 10

```javascript
for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) {
    console.log(i);
  }
}
```

**Output:**

```
2
4
6
8
10
```

---

## 2. `while` Loop

The **while loop** runs as long as the condition is true.

### Example 3: Print numbers 1 to 5

```javascript
let i = 1;
while (i <= 5) {
  console.log(i);
  i++;
}
```

---

## 3. `do...while` Loop

The **do...while loop** runs the code **at least once** before checking the condition.

### Example 4: Print numbers 1 to 5

```javascript
let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 5);
```

---

## 4. Loops with Arrays

Arrays store multiple values, and loops help us go through them.

### Example 5: Print all fruits

```javascript
let fruits = ["Apple", "Banana", "Mango", "Orange"];

for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

---

### Example 6: Print odd numbers from an array

```javascript
let numbers = [2, 5, 8, 11, 14, 17];

for (let i = 0; i < numbers.length; i++) {
  if (numbers[i] % 2 !== 0) {
    console.log(numbers[i]);
  }
}
```

**Output:**

```
5
11
17
```

---

### Example 7: Search for a student

```javascript
let students = ["Ali", "Sara", "Ahmed", "Fatima"];
let searchName = "Ahmed";
let found = false;

for (let i = 0; i < students.length; i++) {
  if (students[i] === searchName) {
    console.log(searchName + " found at index " + i);
    found = true;
    break;
  }
}

if (!found) {
  console.log(searchName + " not found");
}
```

---

## 5. Flag Concept

A **flag** is a variable (true/false) used to keep track of something inside a loop.
In Example 7, we used a flag `found` to check whether the student existed in the array or not.

---

## 6. Practice Problems

Now let’s try some **extra problems** with solutions.

---

### Problem 1: Sum of numbers from 1 to 10

```javascript
let sum = 0;

for (let i = 1; i <= 10; i++) {
  sum = sum + i;
}

console.log("Sum is: " + sum);
```

**Output:**

```
Sum is: 55
```

**Explanation:**

We start with sum = 0.  
The loop runs from i = 1 to i = 10.  
In each step, the current i is added to sum.  
Finally, after the loop, sum contains 1+2+3+...+10 = 55.

---

### Problem 2: Find the largest number in an array

```javascript
let numbers = [12, 45, 67, 23, 89, 34];
let max = numbers[0]; // assume first number is max

for (let i = 1; i < numbers.length; i++) {
  if (numbers[i] > max) {
    max = numbers[i];
  }
}

console.log("Largest number is: " + max);
```

**Output:**

```
Largest number is: 89
```

**Explanation:**

We take the first element numbers[0] as the largest initially.  
The loop goes through the array starting from the second element.  
If we find a number greater than max, we update max.  
At the end, max holds the largest number.

---

### Problem 3: Count how many even numbers are in an array

```javascript
let numbers = [2, 5, 8, 11, 14, 17, 20];
let count = 0;

for (let i = 0; i < numbers.length; i++) {
  if (numbers[i] % 2 === 0) {
    count++;
  }
}

console.log("Total even numbers: " + count);
```

**Output:**

```
Total even numbers: 3
```

**Explanation:**

We start with count = 0.  
The loop checks every number in the array.  
If the number is divisible by 2 (% 2 === 0), then it is even.  
Each time we find an even number, we increase count by 1.  
Finally, count shows how many even numbers exist.

---

### Problem 4: Reverse an array using loop

```javascript
let items = ["A", "B", "C", "D"];
let reversed = [];

for (let i = items.length - 1; i >= 0; i--) {
  reversed.push(items[i]);
}

console.log(reversed);
```

**Output:**

```
["D", "C", "B", "A"]
```

**Explanation:**

We start the loop from the last index (items.length - 1).  
In each step, we take the current element and add it to the reversed array using push().  
This way, elements are added in opposite order.  
At the end, reversed contains the array reversed.

---

### Problem 5: Find if a number exists in an array

```javascript
let numbers = [3, 6, 9, 12, 15];
let searchNumber = 12;
let found = false;

for (let i = 0; i < numbers.length; i++) {
  if (numbers[i] === searchNumber) {
    console.log(searchNumber + " exists in the array");
    found = true;
    break;
  }
}

if (!found) {
  console.log(searchNumber + " not found in the array");
}
```

**Output:**

```
12 exists in the array
```

**Explanation:**

We use a flag variable found = false at the start.  
The loop checks each element of the array.  
If the element matches searchNumber, we print a success message, set found = true, and stop the loop using break.  
If the loop finishes without finding the number, then found remains false and we print “not found”.

---

## ✅ Summary

* Loops repeat tasks without writing the same code many times.
* `for` → best when we know how many times.
* `while` → runs while condition is true.
* `do...while` → runs at least once.
* Arrays + loops = very powerful (searching, filtering, calculating).
* Flag is a helper variable to track results.
* Practice problems make the concept clear.
