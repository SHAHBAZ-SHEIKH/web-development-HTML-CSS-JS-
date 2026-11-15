# JavaScript: Arrays aur Array Methods

> **Note:** Is lecture mein hum pehle **Array** ko zero se samjhenge (kya hai, kyun use hota hai, syntax, index, `length`), phir **Array Methods** (`push`, `pop`, `shift`, `unshift` aur baqi), aur aakhir mein **Practice Questions**.
>
> **Output ke bare mein:** Console mein array aksar `(3) ['Apple', 'Banana', 'Mango']` ki shakal mein nazar aata hai. Is lecture mein samajhne ki asaani ke liye array ko `["Apple", "Banana", "Mango"]` likha gaya hai.

---

## Lecture Roadmap

| Step | Topic | Maqsad |
| --- | --- | --- |
| 1 | Array kya hai? | Concept samajhna |
| 2 | Array kyun use karte hain? | Variables ka masla samajhna |
| 3 | Array ka Syntax aur Index | Array banana aur values access karna |
| 4 | Value badalna aur `length` | Update karna aur size jaanna |
| 5 | Method kya hota hai? | Methods ka concept |
| 6 | `push()` aur `pop()` | Aakhir mein add aur remove karna |
| 7 | `unshift()` aur `shift()` | Shuru mein add aur remove karna |
| 8 | Chaaron methods ka muqabla | Farq samajhna |
| 9 | `includes()` aur `indexOf()` | Value dhoondna |
| 10 | `join()`, `reverse()` aur `concat()` | Text banana, ulta karna, jorna |
| 11 | `slice()` aur `splice()` | Array ka hissa nikalna aur badalna |
| 12 | `sort()` | Tarteeb mein lagana |
| 13 | `forEach()` | Har value par kaam karna |
| 14 | Khulasa aur Common Mistakes | Yaad rakhne wali baatein |
| 15 | Practice Questions | Khud karke seekhna |

---

## Diagram kaise parhein? (Pehle yeh samjhein)

Is lecture ke diagrams isi rule par bane hain:

```
┌─────────────┐
│ condition?  │── true ──►  Yeh kaam hoga
└─────────────┘
   │
 false
   │
   ▼
 Agla step
```

**Asaan rule:** Box = sawal. **Right = Haan (true)**. **Neeche = Naa (false)**.

---

## Step 1: Array kya hai?

**Array** ek aisa variable hai jis mein **ek se zyada values** ek hi naam ke neeche, **tarteeb (order)** se store hoti hain.

### Real life example

> Aap ki **shopping list**: ek hi kaghaz par chawal, cheeni, doodh, ande likhe hain. Har cheez ki apni jagah (line number) hai.

| Real life | Array mein kya hai? |
| --- | --- |
| Shopping list (poora kaghaz) | Array |
| Kaghaz par likhi har cheez | Array ki **value (element)** |
| Line number (1, 2, 3...) | **Index** (JavaScript mein 0 se shuru) |

### Doosri misalein

- **Class ki attendance list:** Saari students ke naam ek jagah.
- **Train ke dibbe:** Ek train, kayi dibbe, har dibbe ka number.
- **Lockers:** Ek line mein kayi lockers, har locker ka number.

---

## Step 2: Array kyun use karte hain?

### Pehle masla dekhein (array ke baghair)

Agar 5 students ke marks store karne hon:

```javascript
var marks1 = 78;
var marks2 = 85;
var marks3 = 62;
var marks4 = 90;
var marks5 = 55;
```

Agar 100 students hon to 100 variables banane parenge. Yeh mushkil aur lamba hai.

### Array ka hal

```javascript
var marks = [78, 85, 62, 90, 55];
```

Ek hi variable mein saare marks.

### Array kyun use karte hain?

| Fayda | Matlab |
| --- | --- |
| **Ek hi naam** | Bohat se variables ki jagah ek variable |
| **Code chhota** | Kam lines, saaf code |
| **Order** | Values tarteeb mein rehti hain |
| **Methods ke sath asaani** | Add, remove, search jaise kaam ke tayyar tareeqe |
| **Real data** | Students ki list, products ki list, cities ki list |

---

## Step 3: Array ka Syntax aur Index

### Array banana

```javascript
var arrayName = [value1, value2, value3];
```

| Hissa | Matlab |
| --- | --- |
| `var` | Keyword: variable banane ka hukm |
| `arrayName` | Array ka naam (aap khud chunte hain) |
| `[ ]` | **Square brackets**: array yahan se shuru aur khatam |
| `,` | Do values ke darmiyan comma |

### Example 1: Strings ka array

```javascript
var fruits = ["Apple", "Banana", "Mango"];
```

### Example 2: Numbers ka array

```javascript
var marks = [78, 85, 62, 90, 55];
```

### Example 3: Khali array

```javascript
var emptyList = [];
```

**Tip:** Array mein alag alag data types bhi ho sakti hain (jaise `["Ali", 20, true]`), lekin shuruat mein ek array mein ek hi qism ki values rakhein.

### Index kya hai?

Array ki har value ki ek **position number** hoti hai, jisay **index** kehte hain.

**Sab se zaroori baat:** Index **0 se shuru** hota hai, 1 se nahi.

```
Array:   var fruits = ["Apple", "Banana", "Mango"];

Index:        0          1          2
            ┌────────┬──────────┬─────────┐
Value:      │ Apple  │  Banana  │  Mango  │
            └────────┴──────────┴─────────┘
```

| Index | Value |
| --- | --- |
| `0` | `"Apple"` (pehli value) |
| `1` | `"Banana"` (doosri value) |
| `2` | `"Mango"` (teesri value) |

**Real life:** Building mein **ground floor ko 0** kehte hain, phir 1st floor, 2nd floor. Array bhi isi tarah 0 se gintee shuru karta hai.

### Array ki value access karna (parhna)

Syntax: `arrayName[index]`

```javascript
var fruits = ["Apple", "Banana", "Mango"];

console.log(fruits[0]);   // Apple
console.log(fruits[1]);   // Banana
console.log(fruits[2]);   // Mango
```

**Output:**

```text
Apple
Banana
Mango
```

### Agar index maujood na ho to?

```javascript
console.log(fruits[5]);   // undefined
```

Jis index par koi value nahi hoti, wahan `undefined` milta hai.

---

## Step 4: Array ki value badalna aur `length`

### Value badalna

Index ke zariye kisi bhi value ko naya value de sakte hain.

```javascript
var fruits = ["Apple", "Banana", "Mango"];

fruits[1] = "Orange";

console.log(fruits[1]);   // Orange
```

**Output:**

```text
Orange
```

Ab array yeh ban gaya: `["Apple", "Orange", "Mango"]`.

### `length`: Array mein kitni values hain?

`length` batata hai ke array mein **kitni values** hain.

```javascript
var marks = [78, 85, 62, 90, 55];

console.log(marks.length);   // 5
```

**Output:**

```text
5
```

**Note:** `length` ke baad brackets `( )` nahi lagte, kyun ke yeh method nahi balke ek **property** (khasiyat) hai.

### Aakhri value nikalna

Array ka aakhri index hamesha **`length - 1`** hota hai.

```javascript
var cities = ["Karachi", "Lahore", "Islamabad", "Quetta"];

console.log(cities.length);                 // 4
console.log(cities[cities.length - 1]);     // Quetta
```

| Cheez | Value |
| --- | --- |
| `cities.length` | `4` |
| Aakhri index | `4 - 1 = 3` |
| `cities[3]` | `"Quetta"` |

**Yaad rakhein:** Agar array mein 4 values hain to indexes `0, 1, 2, 3` hote hain. Index `4` maujood nahi.

### Array ka Khulasa

| Kaam | Syntax | Example |
| --- | --- | --- |
| Array banana | `var a = [v1, v2];` | `var fruits = ["Apple", "Banana"];` |
| Value parhna | `a[index]` | `fruits[0]` |
| Value badalna | `a[index] = newValue;` | `fruits[1] = "Orange";` |
| Size jaanna | `a.length` | `fruits.length` |
| Aakhri value | `a[a.length - 1]` | `fruits[fruits.length - 1]` |

---

## Step 5: Method kya hota hai?

### Method ka matlab

**Method** ek tayyar **function** hota hai jo kisi cheez (jaise array) ke sath juda hota hai. Hum usay **dot (`.`)** laga kar bulate hain aur uske naam ke baad **brackets `( )`** lagate hain.

```javascript
arrayName.methodName();
```

### Real life example

> **TV ka remote:** TV ek array hai aur remote ke buttons uske methods hain. Aap ko andar ki wiring nahi pata, bas button dabate hain aur kaam ho jata hai.

| Real life | JavaScript mein |
| --- | --- |
| TV | Array |
| Remote ka button | Method |
| Button dabana | Method ko **call** karna |
| Volume badhana | Array mein koi tabdeeli |

### Property aur Method mein farq

| | Property | Method |
| --- | --- | --- |
| Misal | `fruits.length` | `fruits.push("Mango")` |
| Brackets `( )` | **Nahi** lagte | **Lagte** hain |
| Kya hai? | Array ki ek khasiyat (information) | Ek kaam jo array par hota hai |

### Methods kyun use karte hain?

- Har kaam ke liye **khud code likhna** nahi parta.
- Code **chhota aur saaf** rehta hai.
- Programmers ke **tayyar aur tested** tareeqe hain.

### Do zaroori baatein (Pehle se yaad rakhein)

| Baat | Matlab |
| --- | --- |
| **Original array badalta hai?** | Kuch methods asli array ko **badal** dete hain (`push`, `pop`, `sort`...), kuch nahi (`slice`, `concat`...) |
| **Return value** | Method kaam ke baad ek **jawab wapas** de sakta hai, jisay variable mein rakh sakte hain |

---

## Step 6: `push()` aur `pop()` (Aakhir mein kaam)

### Real life example

> **Plates ka dher:** Nai plate hamesha **sab se upar** rakhi jati hai (`push`), aur utaarte waqt bhi **sab se upar wali** plate hi uthti hai (`pop`).

### Diagram

```
 push("Mango")  ──►  ┌───────┬────────┬───────┐  ──►  pop()
                     │ Apple │ Banana │ Mango │
                     └───────┴────────┴───────┘
                                          ▲
                              (aakhir mein kaam hota hai)
```

### 1. `push()`: Aakhir mein value jorna

| | |
| --- | --- |
| **Kya karta hai?** | Array ke **aakhir mein** nayi value jor deta hai |
| **Return karta hai** | Array ki **nayi length** |
| **Original array badalta hai?** | **Haan** |

**Syntax:**

```javascript
arrayName.push(value);
```

**Example:**

```javascript
var fruits = ["Apple", "Banana"];

fruits.push("Mango");

console.log(fruits);          // ["Apple", "Banana", "Mango"]
console.log(fruits.length);   // 3
```

**Ek sath kayi values:**

```javascript
fruits.push("Orange", "Grapes");
console.log(fruits);   // ["Apple", "Banana", "Mango", "Orange", "Grapes"]
```

**Return value:**

```javascript
var cart = ["Rice", "Sugar"];
var newLength = cart.push("Milk");

console.log(newLength);   // 3
```

### 2. `pop()`: Aakhri value hatana

| | |
| --- | --- |
| **Kya karta hai?** | Array ki **aakhri value** hata deta hai |
| **Return karta hai** | Hatai gayi **value** |
| **Original array badalta hai?** | **Haan** |

**Syntax:**

```javascript
arrayName.pop();
```

**Example:**

```javascript
var fruits = ["Apple", "Banana", "Mango"];

var removed = fruits.pop();

console.log(removed);   // Mango
console.log(fruits);    // ["Apple", "Banana"]
```

**Dhyan dein:** `pop()` ke brackets ke andar kuch nahi likhte. Yeh hamesha aakhri value hi hatata hai.

### Dry Run

| Step | Code | Array ki halat | Return value |
| --- | --- | --- | --- |
| Shuru | `var fruits = ["Apple", "Banana"];` | `["Apple", "Banana"]` | |
| 1 | `fruits.push("Mango");` | `["Apple", "Banana", "Mango"]` | `3` |
| 2 | `fruits.pop();` | `["Apple", "Banana"]` | `"Mango"` |

---

## Step 7: `unshift()` aur `shift()` (Shuru mein kaam)

### Real life example

> **Bank ki line:** Jo shakhs line mein **sab se aage** khara hai, uski baari pehle aati hai aur woh nikal jata hai (`shift`). Agar koi VIP aaye to woh **sab se aage** ja kar khara ho jata hai (`unshift`).

### Diagram

```
 unshift("Apple")  ──►  ┌───────┬────────┬───────┐
 shift()  ◄──           │ Apple │ Banana │ Mango │
                        └───────┴────────┴───────┘
                            ▲
                (shuru mein kaam hota hai)
```

### 1. `unshift()`: Shuru mein value jorna

| | |
| --- | --- |
| **Kya karta hai?** | Array ke **shuru mein** nayi value jor deta hai |
| **Return karta hai** | Array ki **nayi length** |
| **Original array badalta hai?** | **Haan** |

**Syntax:**

```javascript
arrayName.unshift(value);
```

**Example:**

```javascript
var days = ["Tue", "Wed"];

days.unshift("Mon");

console.log(days);   // ["Mon", "Tue", "Wed"]
```

**Note:** Baqi saari values ek index aage khisak jati hain (`"Tue"` jo index 0 par thi ab index 1 par aa jati hai).

### 2. `shift()`: Pehli value hatana

| | |
| --- | --- |
| **Kya karta hai?** | Array ki **pehli value** hata deta hai |
| **Return karta hai** | Hatai gayi **value** |
| **Original array badalta hai?** | **Haan** |

**Syntax:**

```javascript
arrayName.shift();
```

**Example:**

```javascript
var queue = ["Ayesha", "Sana", "Hira"];

var served = queue.shift();

console.log(served);   // Ayesha
console.log(queue);    // ["Sana", "Hira"]
```

**Note:** Baqi values ek index peeche aa jati hain (`"Sana"` ab index 0 par hai).

### Dry Run (Bank ki line)

| Step | Code | Array ki halat | Return value |
| --- | --- | --- | --- |
| Shuru | `var queue = ["Ayesha", "Sana", "Hira"];` | `["Ayesha", "Sana", "Hira"]` | |
| 1 | `queue.shift();` | `["Sana", "Hira"]` | `"Ayesha"` |
| 2 | `queue.push("Noor");` | `["Sana", "Hira", "Noor"]` | `3` |
| 3 | `queue.unshift("VIP");` | `["VIP", "Sana", "Hira", "Noor"]` | `4` |

---

## Step 8: Chaaron Methods ka Muqabla

### Yaad rakhne ka asaan tareeqa

```
              Shuru mein                         Aakhir mein
           ┌───────────────┐                 ┌───────────────┐
 Jodna     │   unshift()   │                 │    push()     │
           └───────────────┘                 └───────────────┘
           ┌───────────────┐                 ┌───────────────┐
 Hatana    │    shift()    │                 │     pop()     │
           └───────────────┘                 └───────────────┘
```

| Method | Kahan? | Kaam | Return karta hai |
| --- | --- | --- | --- |
| `push(value)` | Aakhir | Value **jorta** hai | Nayi length |
| `pop()` | Aakhir | Value **hatata** hai | Hatai gayi value |
| `unshift(value)` | Shuru | Value **jorta** hai | Nayi length |
| `shift()` | Shuru | Value **hatata** hai | Hatai gayi value |

### Yaad rakhne ka trick

- Chhote naam wale (`push`, `pop`) **aakhir** ke liye hain.
- Lambe naam wale (`unshift`, `shift`) **shuru** ke liye hain.
- `un` wale (`unshift`) aur `pu` wale (`push`) **jorte** hain; baqi dono **hatate** hain.

---

## Step 9: `includes()` aur `indexOf()` (Value dhoondna)

### Real life example

> Library ka **catalogue**: Pehle pata karte hain ke kitab **maujood hai ya nahi** (`includes`), aur phir yeh ke woh **kis number ki shelf** par hai (`indexOf`).

### 1. `includes()`: Maujood hai ya nahi?

| | |
| --- | --- |
| **Kya karta hai?** | Check karta hai ke value array mein hai ya nahi |
| **Return karta hai** | `true` ya `false` |
| **Original array badalta hai?** | **Nahi** |

**Syntax:**

```javascript
arrayName.includes(value);
```

**Example:**

```javascript
var students = ["Ayesha", "Sana", "Hira"];

console.log(students.includes("Hira"));   // true
console.log(students.includes("Zara"));   // false
```

**`if` ke sath use (sirf ek condition):**

```javascript
var allowedUsers = ["ali", "sara", "noor"];
var user = "sara";

if (allowedUsers.includes(user)) {
  console.log("Access granted");
} else {
  console.log("Access denied");
}
```

**Output:**

```text
Access granted
```

**Note:** `includes()` **chhote bare letters** ka farq karta hai: `"Sara"` aur `"sara"` alag hain.

### 2. `indexOf()`: Value kis index par hai?

| | |
| --- | --- |
| **Kya karta hai?** | Value ka **index** batata hai |
| **Return karta hai** | Index number, ya agar value na mile to **`-1`** |
| **Original array badalta hai?** | **Nahi** |

**Syntax:**

```javascript
arrayName.indexOf(value);
```

**Example:**

```javascript
var cities = ["Karachi", "Lahore", "Islamabad", "Quetta"];

console.log(cities.indexOf("Islamabad"));   // 2
console.log(cities.indexOf("Multan"));      // -1
```

**Yaad rakhein:** `-1` ka matlab hai **"value array mein nahi mili"**.

### Muqabla

| Sawal | Method | Jawab |
| --- | --- | --- |
| "Kya `Lahore` list mein hai?" | `includes("Lahore")` | `true` |
| "`Lahore` kis index par hai?" | `indexOf("Lahore")` | `1` |

---

## Step 10: `join()`, `reverse()` aur `concat()`

### 1. `join()`: Array ko text bana dena

| | |
| --- | --- |
| **Kya karta hai?** | Array ki saari values ko jor kar **ek string** bana deta hai |
| **Return karta hai** | String |
| **Original array badalta hai?** | **Nahi** |

**Syntax:**

```javascript
arrayName.join(separator);
```

**Example:**

```javascript
var names = ["Ayesha", "Sana", "Hira"];

console.log(names.join(", "));     // Ayesha, Sana, Hira
console.log(names.join(" - "));    // Ayesha - Sana - Hira
console.log(names.join(""));       // AyeshaSanaHira
```

**Real life:** Dukan ki list ek line mein likhna: `"Rice, Sugar, Milk"`.

### 2. `reverse()`: Array ulta karna

| | |
| --- | --- |
| **Kya karta hai?** | Array ki tarteeb **ulti** kar deta hai |
| **Return karta hai** | Ulta hua array |
| **Original array badalta hai?** | **Haan** |

**Example:**

```javascript
var numbers = [1, 2, 3, 4, 5];

numbers.reverse();

console.log(numbers.join(" "));   // 5 4 3 2 1
```

**Dhyan dein:** `reverse()` asli array ko **hamesha ke liye** ulta kar deta hai, naya array nahi banata.

### 3. `concat()`: Do arrays ko jorna

| | |
| --- | --- |
| **Kya karta hai?** | Do (ya zyada) arrays ko jor kar **naya array** banata hai |
| **Return karta hai** | Naya array |
| **Original array badalta hai?** | **Nahi** |

**Syntax:**

```javascript
firstArray.concat(secondArray);
```

**Example:**

```javascript
var sectionA = ["Ayesha", "Sana"];
var sectionB = ["Hira", "Noor"];

var allStudents = sectionA.concat(sectionB);

console.log(allStudents.join(", "));   // Ayesha, Sana, Hira, Noor
console.log(allStudents.length);       // 4
console.log(sectionA.length);          // 2 (asli array nahi badla)
```

**Real life:** Do alag classes ki lists ko mila kar ek bari list banana.

---

## Step 11: `slice()` aur `splice()`

Yeh dono ke naam milte julte hain, lekin kaam bilkul alag hain.

| | `slice()` | `splice()` |
| --- | --- | --- |
| **Real life** | Kitab ke kuch pages ki **photocopy** nikalna | Kitab ke pages mein **kaat chhant** karna |
| **Original array badalta hai?** | **Nahi** | **Haan** |

### 1. `slice()`: Array ka hissa nikalna (copy)

| | |
| --- | --- |
| **Kya karta hai?** | Array ka ek hissa **copy** karke naya array banata hai |
| **Return karta hai** | Naya array |
| **Original array badalta hai?** | **Nahi** |

**Syntax:**

```javascript
arrayName.slice(start, end);
```

| Hissa | Matlab |
| --- | --- |
| `start` | Kahan se shuru karna hai (is index **samet**) |
| `end` | Kahan par rukna hai (is index **se pehle tak**, `end` shamil **nahi**) |

**Example:**

```javascript
var nums = [10, 20, 30, 40, 50];

var part = nums.slice(1, 4);

console.log(part.join(", "));   // 20, 30, 40
console.log(nums.length);       // 5 (asli array waisa hi hai)
```

```
Index:     0     1     2     3     4
         ┌────┬─────┬─────┬─────┬────┐
         │ 10 │ 20  │ 30  │ 40  │ 50 │
         └────┴─────┴─────┴─────┴────┘
                ▲                 ▲
            start = 1         end = 4 (yahan se pehle tak)
                └── 20, 30, 40 ──┘
```

**Sirf `start` likhein:** Us index se aakhir tak sab kuch milta hai.

```javascript
console.log(nums.slice(2).join(", "));   // 30, 40, 50
```

### 2. `splice()`: Array mein kaat chhant

| | |
| --- | --- |
| **Kya karta hai?** | Array mein se values **hatata**, **jorta** ya **badalta** hai |
| **Return karta hai** | Hatai gayi values ka array |
| **Original array badalta hai?** | **Haan** |

**Syntax:**

```javascript
arrayName.splice(start, deleteCount, item1, item2, ...);
```

| Hissa | Matlab |
| --- | --- |
| `start` | Kis index se kaam shuru karna hai |
| `deleteCount` | Kitni values **hatani** hain |
| `item1, item2...` | (Optional) Wahan kaun si nayi values **jorni** hain |

#### a) Values hatana

```javascript
var colors = ["Red", "Green", "Blue", "Yellow"];

colors.splice(1, 2);   // index 1 se 2 values hatao

console.log(colors.join(", "));   // Red, Yellow
```

#### b) Values jorna (kuch hatae baghair)

`deleteCount` ko `0` rakhein.

```javascript
var letters = ["A", "D"];

letters.splice(1, 0, "B", "C");   // index 1 par B, C jodo

console.log(letters.join(", "));   // A, B, C, D
```

#### c) Value badalna (replace)

```javascript
var subjects = ["Maths", "Physics", "Chemistry"];

subjects.splice(1, 1, "Biology");   // index 1 ki 1 value hata kar Biology lagao

console.log(subjects.join(", "));   // Maths, Biology, Chemistry
```

### `splice()` ka Khulasa

| Kaam | Code | Matlab |
| --- | --- | --- |
| Hatana | `a.splice(1, 2)` | Index 1 se 2 values hatao |
| Jorna | `a.splice(1, 0, "X")` | Index 1 par `"X"` jodo, kuch mat hatao |
| Badalna | `a.splice(1, 1, "X")` | Index 1 ki 1 value hata kar `"X"` lagao |

---

## Step 12: `sort()` (Tarteeb mein lagana)

### Real life example

> Class ki **attendance list** ko naamon ke **alphabet** ke mutabiq lagana.

### Strings ko sort karna

| | |
| --- | --- |
| **Kya karta hai?** | Array ko tarteeb (order) mein lagata hai |
| **Return karta hai** | Sorted array |
| **Original array badalta hai?** | **Haan** |

```javascript
var names = ["Sana", "Ayesha", "Noor", "Hira"];

names.sort();

console.log(names.join(", "));   // Ayesha, Hira, Noor, Sana
```

### Numbers ko sort karna (Bohat Important)

Seedha `sort()` numbers ko bhi **text (alphabet) ki tarah** sort karta hai, jis se **ghalat** result aata hai.

```javascript
var nums = [10, 9, 100, 1];

nums.sort();

console.log(nums.join(", "));   // 1, 10, 100, 9   (GHALAT!)
```

**Wajah:** `"10"` aur `"100"` text ki tarah `"9"` se pehle aate hain, kyun ke unka pehla akshar `"1"` hai.

**Sahi tareeqa:** `sort()` ke andar **compare function** likhein.

```javascript
// Chhote se bare (Ascending)
nums.sort(function (a, b) {
  return a - b;
});

console.log(nums.join(", "));   // 1, 9, 10, 100
```

```javascript
// Bare se chhote (Descending)
nums.sort(function (a, b) {
  return b - a;
});

console.log(nums.join(", "));   // 100, 10, 9, 1
```

| Kaam | Compare function |
| --- | --- |
| Chhote se bare (Ascending) | `return a - b;` |
| Bare se chhote (Descending) | `return b - a;` |

**Abhi ke liye:** Compare function ko ek **formula** ki tarah yaad kar lein. Iski tafseel functions ke lecture mein aayegi.

---

## Step 13: `forEach()` (Har value par kaam)

### Real life example

> Teacher kehti hain: **"Har student ko ek ek kar ke bulao aur uska naam parho."** Har student ke liye wohi kaam dohraya jata hai.

`forEach()` array ki **har value par ek hi kaam** karta hai, ek ke baad ek, shuru se aakhir tak.

| | |
| --- | --- |
| **Kya karta hai?** | Array ki **har value** ke liye ek function chalata hai |
| **Return karta hai** | Kuch nahi |
| **Original array badalta hai?** | Nahi (khud nahi badalta) |

### Syntax

```javascript
arrayName.forEach(function (item) {
  // Har value ke liye yeh code chalega
});
```

| Hissa | Matlab |
| --- | --- |
| `forEach` | Method ka naam |
| `function (item)` | Ek chhota function, jo har value ke liye chalta hai |
| `item` | Is waqt ki value (naam aap khud rakh sakte hain) |

### Example 1: Har fruit print karna

```javascript
var fruits = ["Apple", "Banana", "Mango"];

fruits.forEach(function (fruit) {
  console.log(fruit);
});
```

**Output:**

```text
Apple
Banana
Mango
```

### Diagram

```
 ["Apple", "Banana", "Mango"]
      │         │         │
      ▼         ▼         ▼
 function   function   function
 (fruit)    (fruit)    (fruit)
      │         │         │
      ▼         ▼         ▼
   Apple     Banana     Mango     (har value par wohi kaam)
```

### Example 2: Index bhi chahiye to

Function mein **doosra naam** likhein. Pehla hamesha **value** hota hai, doosra hamesha **index**.

```javascript
var fruits = ["Apple", "Banana", "Mango"];

fruits.forEach(function (fruit, index) {
  console.log(index + ": " + fruit);
});
```

**Output:**

```text
0: Apple
1: Banana
2: Mango
```

### Dry Run

| Chakkar | `fruit` | `index` | Output |
| --- | --- | --- | --- |
| 1 | `"Apple"` | 0 | `0: Apple` |
| 2 | `"Banana"` | 1 | `1: Banana` |
| 3 | `"Mango"` | 2 | `2: Mango` |

### Example 3: Total nikalna

```javascript
var prices = [250, 400, 150];
var total = 0;

prices.forEach(function (price) {
  total = total + price;
});

console.log(total);   // 800
```

**Dry Run:**

| Chakkar | `price` | `total = total + price` | `total` ki nayi value |
| --- | --- | --- | --- |
| Shuru mein | | | `0` |
| 1 | 250 | `0 + 250` | `250` |
| 2 | 400 | `250 + 400` | `650` |
| 3 | 150 | `650 + 150` | `800` |

**Zaroori:** `total` ko `forEach` se **pehle** `0` par set karein.

**Note:** Function ki tafseel aur loops (`for`) ka lecture alag hoga. Abhi `forEach` ko "har value par kaam karne ka tareeqa" samajh lein.

---

## Step 14: Khulasa aur Common Mistakes

### Saare Methods ka Khulasa

| Method | Kaam | Original array badalta hai? | Return karta hai |
| --- | --- | --- | --- |
| `push(v)` | Aakhir mein jorna | **Haan** | Nayi length |
| `pop()` | Aakhri hatana | **Haan** | Hatai gayi value |
| `unshift(v)` | Shuru mein jorna | **Haan** | Nayi length |
| `shift()` | Pehli hatana | **Haan** | Hatai gayi value |
| `includes(v)` | Maujood hai? | Nahi | `true` / `false` |
| `indexOf(v)` | Index dhoondna | Nahi | Index ya `-1` |
| `join(sep)` | String banana | Nahi | String |
| `reverse()` | Ulta karna | **Haan** | Ulta array |
| `concat(arr)` | Arrays jorna | Nahi | Naya array |
| `slice(s, e)` | Hissa copy karna | Nahi | Naya array |
| `splice(s, n, ...)` | Hatana, jorna, badalna | **Haan** | Hatai gayi values |
| `sort()` | Tarteeb lagana | **Haan** | Sorted array |
| `forEach(fn)` | Har value par kaam | Nahi (khud nahi badalta) | Kuch nahi |

### Common Mistakes (Aam Ghaltiyan)

| Ghalat | Sahi | Wajah |
| --- | --- | --- |
| `var fruits = ("Apple", "Banana");` | `var fruits = ["Apple", "Banana"];` | Array ke liye **square brackets** `[ ]` use hote hain |
| `fruits[1]` ko pehli value samajhna | `fruits[0]` pehli value hai | Index **0 se** shuru hota hai |
| `fruits.push["Mango"];` | `fruits.push("Mango");` | Method ke liye **round brackets** `( )` lagte hain, `[ ]` nahi |
| `fruits.pop("Apple");` | `fruits.pop();` | `pop()` hamesha aakhri value hi hatata hai |
| `fruits.length()` | `fruits.length` | `length` property hai, method nahi |
| `var a = fruits.push("X");` aur `a` ko array samajhna | `a` mein **nayi length** hoti hai | `push` array nahi, length return karta hai |
| `slice` aur `splice` ko ek samajhna | `slice` copy karta hai, `splice` asli array badalta hai | Dono ka kaam alag hai |
| `[10, 9, 100].sort()` | `.sort(function (a, b) { return a - b; })` | Seedha `sort()` numbers ko text ki tarah sort karta hai |
| `slice(1, 4)` mein index 4 ki value expect karna | Index 4 **shamil nahi** hoti | `end` se **pehle tak** ki values milti hain |
| `fruits.indexOf("Mango") > 0` se check karna | `fruits.includes("Mango")` ya `!== -1` | Pehli value ka index `0` hai, is liye `> 0` ghalat hai |

---

## Final Revision

| Concept | Yaad rakhein |
| --- | --- |
| Array | Ek variable mein kayi values, tarteeb se |
| Syntax | `var a = [v1, v2, v3];` |
| Index | Position number, **0 se shuru** |
| Value parhna / badalna | `a[0]` / `a[1] = "New";` |
| Size | `a.length` (brackets nahi) |
| Aakhri value | `a[a.length - 1]` |
| Method | Dot se bulaya jane wala tayyar function, brackets `( )` ke sath |
| `push` / `pop` | **Aakhir** mein jodna / hatana |
| `unshift` / `shift` | **Shuru** mein jodna / hatana |
| `push`, `unshift` return | Nayi **length** |
| `pop`, `shift` return | Hatai gayi **value** |
| `includes` | `true` ya `false` |
| `indexOf` | Index, ya value na mile to `-1` |
| `join` | Array se **string** banata hai |
| `reverse` | Asli array ko ulta karta hai |
| `concat` | Do arrays se **naya** array banata hai |
| `slice(s, e)` | **Copy**, `end` shamil nahi, original nahi badalta |
| `splice(s, n, ...)` | **Kaat chhant**, original badalta hai |
| `sort()` | Strings ke liye theek, numbers ke liye compare function |
| Ascending / Descending | `a - b` / `b - a` |
| `forEach` | Har value par ek function chalata hai |

---

## Practice Questions (Students ke liye)

**Hidayat:** Har question mein output dikhane ke liye `console.log()` use karein. Agar ek question mein kayi lines ka output ho to har value alag line mein print hogi. Array ko ek line mein dikhane ke liye `join()` use karein.

### Section A: Array ki Bunyad

**Question 1: Student Names**

- **Scenario:** Ek class teacher ne attendance register mein 4 students ke naam likhe hain.
- **Given:** `var students = ["Ayesha", "Sana", "Hira", "Noor"];`
- **Task:** Array ki **pehli** aur **teesri** value console mein print karein.
- **Expected Output:**

```text
Ayesha
Hira
```

**Question 2: Colour Change**

- **Scenario:** Ek designer ne teen rang chune hain, lekin client ne doosre rang ko Yellow se badalne ko kaha hai.
- **Given:** `var colors = ["Red", "Green", "Blue"];`
- **Task:** Index `1` ki value ko `"Yellow"` se badlein aur phir index `1` ki value print karein.
- **Expected Output:**

```text
Yellow
```

**Question 3: Total Students**

- **Scenario:** Teacher ko jaanna hai ke exam mein kitne students ke marks array mein maujood hain.
- **Given:** `var marks = [78, 85, 62, 90, 55];`
- **Task:** `length` ki madad se marks ki tadaad (count) print karein.
- **Expected Output:**

```text
5
```

**Question 4: Last City**

- **Scenario:** Ek travel app cities ki list rakhti hai aur aakhri city dikhana chahti hai.
- **Given:** `var cities = ["Karachi", "Lahore", "Islamabad", "Quetta"];`
- **Task:** `length` use kar ke array ki **aakhri** value print karein.
- **Expected Output:**

```text
Quetta
```

**Question 5: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var items = ["Pen", "Book", "Bag"];
console.log(items[3]);
```

- **Task:** Output kya hoga aur kyun?
- **Expected Output:** `undefined` (kyun ke array mein 3 values hain, indexes `0, 1, 2` hain, aur index `3` maujood nahi).

### Section B: `push()`, `pop()`, `shift()`, `unshift()`

**Question 6: Shopping Cart**

- **Scenario:** Hira ki online shopping cart mein pehle se do cheezein hain. Usne ek aur cheez cart mein daali.
- **Given:** `var cart = ["Rice", "Sugar"];`
- **Task:** `push()` se `"Milk"` cart ke aakhir mein jorein. Phir cart ki `length` aur aakhri value print karein.
- **Expected Output:**

```text
3
Milk
```

**Question 7: Completed Task**

- **Scenario:** Ek to-do app mein tasks ki list hai. Jab aakhri task mukammal ho jata hai to usay list se hata diya jata hai.
- **Given:** `var tasks = ["Wash", "Cook", "Study"];`
- **Task:** `pop()` se aakhri task hatayein aur hataya gaya task variable `done` mein rakhein. Phir `done` aur `tasks.length` print karein.
- **Expected Output:**

```text
Study
2
```

**Question 8: Bank Queue**

- **Scenario:** Bank mein 3 customers line mein hain. Jo customer sab se aage hai, uski baari aa gayi.
- **Given:** `var queue = ["Ayesha", "Sana", "Hira"];`
- **Task:** `shift()` se pehle customer ko hatayein aur uska naam variable `served` mein rakhein. Phir `served` aur line ka naya pehla customer (`queue[0]`) print karein.
- **Expected Output:**

```text
Ayesha
Sana
```

**Question 9: Week Plan**

- **Scenario:** Ek planner app mein haftay ke din Tuesday se shuru hote hain, lekin Monday bhi shuru mein shamil karna hai.
- **Given:** `var days = ["Tue", "Wed"];`
- **Task:** `unshift()` se `"Mon"` shuru mein jorein. Phir `days[0]` aur `days.length` print karein.
- **Expected Output:**

```text
Mon
3
```

**Question 10: Waiting Line**

- **Scenario:** Ek clinic mein 2 patients intezar kar rahe hain. Ek naya patient aya aur line ke aakhir mein khara ho gaya. Phir pehle patient ko doctor ne bula liya.
- **Given:** `var line = ["Noor", "Hira"];`
- **Task:** `push("Sana")` se naya patient jorein. Phir `shift()` se pehle patient ko hatayein aur uska naam variable `called` mein rakhein. Aakhir mein `called` aur `line.length` print karein.
- **Expected Output:**

```text
Noor
2
```

**Question 11: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var a = [1, 2, 3];

a.push(4);
a.pop();
a.pop();
a.unshift(0);

console.log(a.length);
console.log(a[0]);
```

- **Task:** Har line ke baad array ki halat likhein aur output batayein.
- **Expected Output:**

```text
3
0
```

### Section C: `includes()` aur `indexOf()`

**Question 12: Attendance Check**

- **Scenario:** Teacher ko check karna hai ke kuch naam class ki list mein maujood hain ya nahi.
- **Given:** `var students = ["Ayesha", "Sana", "Hira"];`
- **Task:** `includes()` se `"Hira"` aur `"Zara"` check karein aur dono ke result print karein.
- **Expected Output:**

```text
true
false
```

**Question 13: Login Access**

- **Scenario:** Ek website sirf manzoor shuda users ko andar aane deti hai. Ek user `"noor"` login karna chahti hai.
- **Given:** `var allowedUsers = ["ali", "sara", "noor"];` aur `var user = "noor";`
- **Task:** `if` aur `includes()` se check karein. Agar user list mein hai to `Access granted`, warna `Access denied` print karein.
- **Expected Output:**

```text
Access granted
```

**Question 14: City Position**

- **Scenario:** Ek travel app cities ki list mein ek city ki position dikhati hai. Agar city list mein na ho to `-1` dikhati hai.
- **Given:** `var cities = ["Karachi", "Lahore", "Islamabad", "Quetta"];`
- **Task:** `indexOf()` se `"Islamabad"` aur `"Multan"` ke indexes print karein.
- **Expected Output:**

```text
2
-1
```

**Question 15: Stock Check**

- **Scenario:** Ek stationery shop ke paas kuch cheezein hain. Customer ne `"Marker"` maanga.
- **Given:** `var stock = ["Pen", "Book", "Bag"];` aur `var item = "Marker";`
- **Task:** `if` aur `includes()` se check karein. Agar item stock mein hai to `Available`, warna `Out of stock` print karein.
- **Expected Output:**

```text
Out of stock
```

### Section D: `join()`, `reverse()`, `concat()`

**Question 16: Name List**

- **Scenario:** Ek report mein students ke naam ek hi line mein coma se alag karke likhne hain.
- **Given:** `var names = ["Ayesha", "Sana", "Hira"];`
- **Task:** `join(", ")` se saare naam ek line mein print karein.
- **Expected Output:**

```text
Ayesha, Sana, Hira
```

**Question 17: Rank Reversal**

- **Scenario:** Ek competition mein ranks 1 se 5 tak hain, lekin result board par ulte (5 se 1) dikhane hain.
- **Given:** `var ranks = [1, 2, 3, 4, 5];`
- **Task:** `reverse()` se array ulta karein, phir `join(" ")` se ek line mein print karein.
- **Expected Output:**

```text
5 4 3 2 1
```

**Question 18: Merge Sections**

- **Scenario:** School mein do sections ki lists ko mila kar ek class list banani hai.
- **Given:** `var sectionA = ["Ayesha", "Sana"];` aur `var sectionB = ["Hira", "Noor"];`
- **Task:** `concat()` se dono arrays jor kar `allStudents` banayein. Phir `allStudents.length` aur `allStudents.join(", ")` print karein.
- **Expected Output:**

```text
4
Ayesha, Sana, Hira, Noor
```

**Question 19: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var nums = [1, 2, 3];

nums.reverse();

console.log(nums[0]);
console.log(nums.join(""));
```

- **Task:** Output batayein aur wajah likhein ke `reverse()` ne asli array ke sath kya kiya.
- **Expected Output:**

```text
3
321
```

### Section E: `slice()` aur `splice()`

**Question 20: Top 3 Students**

- **Scenario:** School ko 5 students ke marks mein se pehle 3 (top 3) announce karne hain, lekin asli list mehfooz rakhni hai.
- **Given:** `var marks = [95, 90, 85, 80, 75];`
- **Task:** `slice(0, 3)` se top 3 marks `top3` mein rakhein. Phir `top3.join(", ")` aur `marks.length` print karein.
- **Expected Output:**

```text
95, 90, 85
5
```

**Question 21: Remaining Months**

- **Scenario:** Saal ke shuru ke 5 mahine list mein hain. Ek app ko index 2 (March) se aakhir tak ke mahine dikhane hain.
- **Given:** `var months = ["Jan", "Feb", "Mar", "Apr", "May"];`
- **Task:** `slice(2)` se mahine nikal kar `join(", ")` ke sath print karein.
- **Expected Output:**

```text
Mar, Apr, May
```

**Question 22: Remove Colours**

- **Scenario:** Ek designer ke paas 4 rang hain. Beech ke do rang (Green aur Blue) hatane hain.
- **Given:** `var colors = ["Red", "Green", "Blue", "Yellow"];`
- **Task:** `splice(1, 2)` se do rang hatayein aur `colors.join(", ")` print karein.
- **Expected Output:**

```text
Red, Yellow
```

**Question 23: Add Missing Letters**

- **Scenario:** Ek alphabet list mein beech ke do huroof (B aur C) reh gaye hain.
- **Given:** `var letters = ["A", "D"];`
- **Task:** `splice()` se index `1` par `"B"` aur `"C"` jorein (kuch hatae baghair). Phir `letters.join(", ")` print karein.
- **Expected Output:**

```text
A, B, C, D
```

**Question 24: Replace Subject**

- **Scenario:** Ek time table mein Physics ki jagah Biology rakhni hai.
- **Given:** `var subjects = ["Maths", "Physics", "Chemistry"];`
- **Task:** `splice()` se index `1` ki value `"Biology"` se badlein aur `subjects.join(", ")` print karein.
- **Expected Output:**

```text
Maths, Biology, Chemistry
```

### Section F: `sort()` aur `forEach()`

**Question 25: Alphabetical List**

- **Scenario:** Class teacher ko attendance sheet naamon ke alphabet ke mutabiq tayyar karni hai.
- **Given:** `var names = ["Sana", "Ayesha", "Noor", "Hira"];`
- **Task:** `sort()` se naam tarteeb mein lagayein aur `join(", ")` se print karein.
- **Expected Output:**

```text
Ayesha, Hira, Noor, Sana
```

**Question 26: Marks Ascending**

- **Scenario:** Ek teacher ko 4 students ke marks chhote se bare tarteeb mein dikhane hain.
- **Given:** `var marks = [70, 9, 100, 45];`
- **Task:** Compare function (`a - b`) ke sath `sort()` use karein aur `join(", ")` se print karein.
- **Expected Output:**

```text
9, 45, 70, 100
```

**Question 27: Scores Descending**

- **Scenario:** Ek game mein scores ko bare se chhote tarteeb mein leaderboard par dikhana hai.
- **Given:** `var scores = [55, 92, 67, 80];`
- **Task:** Compare function (`b - a`) ke sath `sort()` use karein aur `join(", ")` se print karein.
- **Expected Output:**

```text
92, 80, 67, 55
```

**Question 28: Fruit Messages**

- **Scenario:** Ek app har fruit ke liye ek message dikhati hai.
- **Given:** `var fruits = ["Apple", "Banana", "Mango"];`
- **Task:** `forEach()` se har fruit ke liye `I like <fruit>` print karein.
- **Expected Output:**

```text
I like Apple
I like Banana
I like Mango
```

**Question 29: Shopping Total**

- **Scenario:** Maryam ne 3 cheezein khareedi hain aur cashier ko `forEach()` se total bill nikalna hai.
- **Given:** `var prices = [250, 400, 150];` aur `var total = 0;`
- **Task:** `forEach()` se saari qeematon ka total `total` mein jama karein aur print karein.
- **Expected Output:**

```text
800
```

### Section G: Predict the Output aur Debugging

**Question 30: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var items = ["A", "B", "C", "D"];

var removed = items.splice(1, 2);

console.log(removed.join(""));
console.log(items.join(""));
```

- **Task:** Dono lines ka output batayein. `removed` aur `items` mein kya kya hai?
- **Expected Output:**

```text
BC
AD
```

**Question 31: Debugging (Ghalti dhundein)**

- **Scenario:** Ek student ne array mein `"Mango"` jorne ka code likha, lekin `length` phir bhi `2` aa rahi hai.

```javascript
var fruits = ["Apple", "Banana"];

fruits.push["Mango"];

console.log(fruits.length);
```

- **Task:** Ghalti dhundein, usay theek karein, aur batayein ke ghalti kyun thi.
- **Hint:** Method ko bulane ke liye kaun se brackets lagte hain?
- **Expected Output (theek code ke baad):**

```text
3
```
