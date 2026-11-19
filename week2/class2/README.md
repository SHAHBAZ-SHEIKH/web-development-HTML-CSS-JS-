# JavaScript: for Loop

> **Note:** Is lecture mein hum **Loop** ka concept, **`for` loop** ka syntax, uske teen hisse, diagram aur dry run, aur phir **Array ke sath `for` loop** seekhenge. Array ki bunyad pichle lecture mein ho chuki hai, is liye wahan sirf ek chhota recap hai.

---

## Lecture Roadmap

| Step | Topic | Maqsad |
| --- | --- | --- |
| 1 | Loop kya hai? | Repetition ka concept |
| 2 | `for` loop ka Syntax | Teen hisse samajhna |
| 3 | `for` loop kaise kaam karta hai | Diagram aur dry run |
| 4 | `for` loop ke Examples | Counting, countdown, table, sum |
| 5 | Array ke sath `for` loop | Dono ko mila kar use karna |
| 6 | Common Mistakes | Aam ghaltiyan aur infinite loop |
| 7 | Practice Questions | Khud karke seekhna |

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

## Step 1: Loop kya hai?

### Pehle masla dekhein

Agar `"Hello"` 5 baar print karna ho:

```javascript
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
```

Agar 1000 baar print karna ho to 1000 lines likhni parengi, jo mumkin nahi.

### Loop ka hal

**Loop** ek aisa tareeqa hai jis se hum **ek kaam ko bar bar (repeat)** karwate hain, jab tak ek condition sahi rehti hai.

### Real life example

> Teacher kehti hain: **"Jab tak 10 sit-ups poore na ho jayein, sit-ups karti raho."**
>
> Aap ek sit-up karti hain, gintee badhati hain (1, 2, 3...), aur 10 par ruk jati hain.

| Real life | Loop mein |
| --- | --- |
| Gintee shuru karna (1) | **Initialization** |
| "10 tak karna hai" | **Condition** |
| Har sit-up ke baad gintee badhana | **Update** |
| Sit-up karna | **Loop ka kaam (body)** |

### Loop kyun use karte hain?

- Ek kaam **bohat baar** karne ke liye, kam code mein.
- Array ki **saari values** ko ek ek kar ke parhne ke liye.
- Numbers ki table, counting, total nikalne ke liye.

JavaScript mein kayi loops hain. Hum sab se pehle **`for` loop** seekhenge.

---

## Step 2: `for` Loop ka Syntax

```javascript
for (initialization; condition; update) {
  // Yeh code bar bar chalega
}
```

### Teen hisse

| Hissa | Kaam | Example | Kab chalta hai? |
| --- | --- | --- | --- |
| **Initialization** | Gintee ka variable banana aur shuru ki value dena | `var i = 1` | Sirf **ek baar**, shuru mein |
| **Condition** | Check karna ke loop chalana hai ya nahi | `i <= 5` | Har chakkar (iteration) se **pehle** |
| **Update** | Gintee ko badhana ya ghatana | `i++` | Har chakkar ke **baad** |

**Note:** Teeno hisse `;` (semicolon) se alag hote hain.

### `i++` ka matlab

| Likha hua | Matlab |
| --- | --- |
| `i++` | `i` mein 1 jama karo (`i = i + 1`) |
| `i--` | `i` mein se 1 kam karo (`i = i - 1`) |
| `i += 2` | `i` mein 2 jama karo (`i = i + 2`) |

**Tip:** Gintee ke variable ka naam aam taur par `i` rakhte hain (iteration ke liye).

### Pseudo Code

```text
START
  i ko 1 se shuru karo
  JAB TAK i 5 se chhota ya barabar hai:
      "Hello" dikhao
      i mein 1 jama karo
  END
END
```

---

## Step 3: `for` Loop kaise kaam karta hai?

### Diagram

```
   START
     │
     ▼
 var i = 1            ◄── Initialization (sirf ek baar)
     │
     ▼
┌──────────┐
│ i <= 5 ? │── false ──►  Loop khatam, aage ka code
└──────────┘
     │
   true
     │
     ▼
 Body: console.log(i)
     │
     ▼
 i++                  ◄── Update
     │
     └────────────►  wapas Condition check karne jao
```

**Diagram kaise parhein:**

1. Pehle `i = 1` set hota hai (sirf ek baar).
2. Condition check hoti hai. **True** ho to neeche body chalti hai.
3. Body ke baad `i++` hota hai.
4. Phir wapas condition check hoti hai.
5. Jab condition **false** ho jaye, loop ruk jata hai.

### Pehla Example

```javascript
for (var i = 1; i <= 5; i++) {
  console.log(i);
}
```

**Output:**

```text
1
2
3
4
5
```

### Dry Run (har chakkar ka hisaab)

| Chakkar | `i` ki value | Condition `i <= 5` | Action | Update ke baad `i` |
| --- | --- | --- | --- | --- |
| 1 | 1 | true | `1` print | 2 |
| 2 | 2 | true | `2` print | 3 |
| 3 | 3 | true | `3` print | 4 |
| 4 | 4 | true | `4` print | 5 |
| 5 | 5 | true | `5` print | 6 |
| 6 | 6 | **false** | Loop **ruk gaya** | |

**Dhyan dein:** Jab `i = 6` hua, to condition `6 <= 5` false thi, is liye loop ki body nahi chali.

---

## Step 4: `for` Loop ke Examples

### Example 1: "Hello" 3 baar

```javascript
for (var i = 1; i <= 3; i++) {
  console.log("Hello");
}
```

**Output:**

```text
Hello
Hello
Hello
```

### Example 2: Ginti ulti (Countdown)

Yahan `i--` use hota hai aur condition `i >= 1` hai.

```javascript
for (var i = 5; i >= 1; i--) {
  console.log(i);
}
```

**Output:**

```text
5
4
3
2
1
```

### Example 3: Number ki Table (2 ki table)

```javascript
for (var i = 1; i <= 5; i++) {
  console.log("2 x " + i + " = " + (2 * i));
}
```

**Output:**

```text
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
```

**Tip:** Text aur number ko jorne ke liye `+` use hota hai. Hisaab ko brackets `( )` mein likhein.

### Example 4: Even numbers (2 ke qadam se)

Yahan `i += 2` use hota hai.

```javascript
for (var i = 2; i <= 10; i += 2) {
  console.log(i);
}
```

**Output:**

```text
2
4
6
8
10
```

### Example 5: 1 se 5 tak ka Total (Sum)

```javascript
var sum = 0;

for (var i = 1; i <= 5; i++) {
  sum = sum + i;
}

console.log(sum);
```

**Output:**

```text
15
```

**Dry Run:**

| Chakkar | `i` | `sum = sum + i` | `sum` ki nayi value |
| --- | --- | --- | --- |
| Shuru mein | | | `0` |
| 1 | 1 | `0 + 1` | `1` |
| 2 | 2 | `1 + 2` | `3` |
| 3 | 3 | `3 + 3` | `6` |
| 4 | 4 | `6 + 4` | `10` |
| 5 | 5 | `10 + 5` | `15` |

**Real life:** Piggy bank mein roz paise daalna. `sum` piggy bank hai aur `i` har roz ke paise.

**Zaroori:** `sum` ko loop se **pehle** `0` par set karein, loop ke **andar** nahi.

### Example 6: Loop ke andar `if` (sirf ek condition)

1 se 6 tak mein se sirf **even** numbers print karein.

```javascript
for (var i = 1; i <= 6; i++) {
  if (i % 2 === 0) {
    console.log(i);
  }
}
```

**Output:**

```text
2
4
6
```

---

## Step 5: Array ke sath `for` Loop

### Pehle yaad karein (Array ka recap)

Pichle lecture mein humne array seekha tha. Sirf teen baatein yaad rakhein:

| Baat | Matlab | Example |
| --- | --- | --- |
| Array | Ek variable mein kayi values | `var fruits = ["Apple", "Banana", "Mango"];` |
| Index | Position number, **0 se shuru** | `fruits[0]` yaani `"Apple"` |
| `length` | Array mein kitni values hain | `fruits.length` yaani `3` |


Array aur loop ek dusre ke **sab se achhe saathi** hain. Loop ki gintee ko array ka **index** bana dete hain.

### Pseudo Code

```text
START
  array banao
  i ko 0 se shuru karo
  JAB TAK i array ki length se chhota hai:
      array ki i-th value dikhao
      i mein 1 jama karo
  END
END
```

### Syntax

```javascript
for (var i = 0; i < arrayName.length; i++) {
  console.log(arrayName[i]);
}
```

| Hissa | Wajah |
| --- | --- |
| `var i = 0` | Index **0 se** shuru hota hai |
| `i < arrayName.length` | Aakhri index `length - 1` hai, is liye `<` use hota hai (`<=` nahi) |
| `i++` | Har chakkar mein agla index |
| `arrayName[i]` | Is waqt ke index ki value |

### Example 1: Saari fruits print karna

```javascript
var fruits = ["Apple", "Banana", "Mango"];

for (var i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

**Output:**

```text
Apple
Banana
Mango
```

### Dry Run

| Chakkar | `i` | `i < 3` | `fruits[i]` | Output |
| --- | --- | --- | --- | --- |
| 1 | 0 | true | `"Apple"` | Apple |
| 2 | 1 | true | `"Banana"` | Banana |
| 3 | 2 | true | `"Mango"` | Mango |
| 4 | 3 | **false** | | Loop ruk gaya |

### Diagram

```
 var i = 0
     │
     ▼
┌───────────────────┐
│ i < fruits.length │── false ──►  Loop khatam
└───────────────────┘
     │
   true
     │
     ▼
 console.log(fruits[i])
     │
     ▼
 i++
     │
     └────────────►  wapas condition par
```

### Example 2: Marks ka Total

```javascript
var marks = [78, 85, 62, 90, 55];
var total = 0;

for (var i = 0; i < marks.length; i++) {
  total = total + marks[i];
}

console.log(total);
```

**Output:**

```text
370
```

**Hisaab:** `78 + 85 + 62 + 90 + 55 = 370`

### Example 3: Marks ka Average

```javascript
var marks = [78, 85, 62, 90, 55];
var total = 0;

for (var i = 0; i < marks.length; i++) {
  total = total + marks[i];
}

var average = total / marks.length;
console.log(average);
```

**Output:**

```text
74
```

### Example 4: Sab se zyada marks (Highest)

```javascript
var marks = [45, 82, 67, 91, 58];
var highest = marks[0];

for (var i = 1; i < marks.length; i++) {
  if (marks[i] > highest) {
    highest = marks[i];
  }
}

console.log(highest);
```

**Output:**

```text
91
```

**Kaise kaam karta hai:** Pehle pehli value ko sab se bara maan lete hain. Phir har agli value ka muqabla karte hain. Jo value bari ho, usay `highest` bana dete hain.

### Example 5: Pass hone wale students ginna (Counting)

```javascript
var marks = [45, 72, 38, 66, 90, 49];
var passed = 0;

for (var i = 0; i < marks.length; i++) {
  if (marks[i] >= 50) {
    passed = passed + 1;
  }
}

console.log(passed);
```

**Output:**

```text
3
```

**Wajah:** Sirf `72`, `66` aur `90` ke marks `50` ya us se zyada hain.

### Example 6: Array ulta (Reverse) print karna

```javascript
var days = ["Mon", "Tue", "Wed", "Thu"];

for (var i = days.length - 1; i >= 0; i--) {
  console.log(days[i]);
}
```

**Output:**

```text
Thu
Wed
Tue
Mon
```

**Dhyan dein:** Ulta chalne ke liye `length - 1` se shuru karte hain, `i--` karte hain, aur condition `i >= 0` hoti hai.

---

## Step 6: Common Mistakes (Aam Ghaltiyan)

| Ghalat | Sahi | Wajah |
| --- | --- | --- |
| `var fruits = ("Apple", "Banana");` | `var fruits = ["Apple", "Banana"];` | Array ke liye **square brackets** `[ ]` use hote hain |
| `fruits[1]` ko pehli value samajhna | `fruits[0]` pehli value hai | Index **0 se** shuru hota hai |
| `fruits.length()` | `fruits.length` | `length` ke baad brackets nahi lagte |
| `for (var i = 0; i <= fruits.length; i++)` | `for (var i = 0; i < fruits.length; i++)` | `<=` se aakhri chakkar mein `undefined` aata hai |
| `for (var i = 1, i <= 5, i++)` | `for (var i = 1; i <= 5; i++)` | Teeno hisse `;` se alag hote hain |
| `for (var i = 1; i <= 5; i--)` | `for (var i = 1; i <= 5; i++)` | Ghalat update se loop kabhi nahi rukta |
| `var sum = 0;` loop ke **andar** likhna | `var sum = 0;` loop se **pehle** likhna | Warna har chakkar mein sum dobara `0` ho jata hai |

### Infinite Loop (Kabhi na rukne wala loop)

Agar condition kabhi false na ho, to loop **hamesha chalta rehta hai** aur browser atak (hang) sakta hai.

```javascript
// Ghalat: i kabhi 5 se bara nahi hoga
for (var i = 1; i <= 5; i--) {
  console.log(i);
}
```

**Hal:** Hamesha check karein ke update (`i++` ya `i--`) condition ko **false ki taraf** le ja raha hai.

### `<` ya `<=` kab use karein?

| Situation | Condition |
| --- | --- |
| Numbers 1 se 5 tak (5 bhi shamil) | `i <= 5` |
| Array ke saare indexes (0 se `length - 1`) | `i < arrayName.length` |

---

## Final Revision

| Concept | Yaad rakhein |
| --- | --- |
| Loop | Kaam ko bar bar chalana |
| `for` ke 3 hisse | Initialization; Condition; Update |
| Initialization | Sirf ek baar chalta hai |
| Condition | Har chakkar se pehle check hoti hai |
| Update | Har chakkar ke baad chalta hai |
| `i++` / `i--` | 1 barhana / 1 ghatana |
| `i += 2` | 2 ke qadam se barhna |
| Chakkar (Iteration) | Loop ka ek baar chalna |
| Total nikalna | `sum` ko loop se pehle `0` par set karein |
| Guna (product) nikalna | `fact` ko loop se pehle `1` par set karein |
| Array ka loop | `for (var i = 0; i < a.length; i++)` |
| Array mein `<` kyun? | Aakhri index `length - 1` hota hai |
| Ulta chalna | `var i = a.length - 1; i >= 0; i--` |
| Infinite loop | Condition kabhi false na ho to loop nahi rukta |

---

## Practice Questions (Students ke liye)

**Hidayat:** Har question mein output dikhane ke liye `console.log()` use karein. Agar ek question mein kayi lines ka output ho to har value alag line mein print hogi.

### Section A: `for` Loop ki Bunyad

**Question 1: Attendance Counting**

- **Scenario:** Teacher roll call mein 1 se 10 tak roll numbers parhti hain.
- **Task:** `for` loop se `1` se `10` tak ke numbers print karein.
- **Expected Output:**

```text
1
2
3
4
5
6
7
8
9
10
```

**Question 2: Rocket Countdown**

- **Scenario:** Ek rocket launch se pehle countdown 5 se shuru ho kar 1 tak jata hai.
- **Task:** `for` loop se `5` se `1` tak ulti ginti print karein.
- **Expected Output:**

```text
5
4
3
2
1
```

**Question 3: Table of 3**

- **Scenario:** Ek primary class mein bachon ko 3 ki table yaad karwani hai.
- **Task:** `for` loop se 3 ki table (`1` se `10` tak) is format mein print karein: `3 x 1 = 3`.
- **Expected Output:**

```text
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30
```

**Question 4: Even Numbers**

- **Scenario:** Ek math teacher ko 2 se 20 tak ke even numbers board par likhne hain.
- **Task:** `for` loop mein `i += 2` use kar ke `2` se `20` tak ke even numbers print karein.
- **Expected Output:**

```text
2
4
6
8
10
12
14
16
18
20
```

**Question 5: Daily Savings**

- **Scenario:** Maryam roz piggy bank mein utne rupay daalti hai jitni tareekh hoti hai (pehle din 1 rupay, doosre din 2 rupay, aur isi tarah 10 din tak).
- **Given:** `var savings = 0;`
- **Task:** `for` loop se 1 se 10 tak ke numbers `savings` mein jama karein aur aakhir mein `savings` print karein.
- **Expected Output:**

```text
55
```

**Question 6: Odd Numbers**

- **Scenario:** Ek math teacher ko board par 1 se 15 tak ke taaq (odd) numbers likhne hain.
- **Task:** `for` loop mein `var i = 1` se shuru karein aur `i += 2` use kar ke `15` tak ke odd numbers print karein.
- **Expected Output:**

```text
1
3
5
7
9
11
13
15
```

**Question 7: Multiples of 5**

- **Scenario:** Ek dukan mein har 5 rupay ke sikkon ka hisaab rakhna hai.
- **Task:** `for` loop se `5` se `50` tak ke 5 ke multiples (`5, 10, 15, ...`) print karein.
- **Expected Output:**

```text
5
10
15
20
25
30
35
40
45
50
```

**Question 8: Hundred Sum**

- **Scenario:** Ek student ko 1 se 100 tak ke saare numbers ka total nikalna hai.
- **Given:** `var sum = 0;`
- **Task:** `for` loop se `1` se `100` tak ke numbers `sum` mein jama karein aur aakhir mein `sum` print karein.
- **Expected Output:**

```text
5050
```

**Question 9: Factorial**

- **Scenario:** Math mein 5 ka factorial `5 x 4 x 3 x 2 x 1` hota hai. Ek calculator app yeh hisaab loop se karti hai.
- **Given:** `var fact = 1;`
- **Task:** `for` loop se `1` se `5` tak ke numbers ko `fact` mein guna (`fact = fact * i`) karein aur aakhir mein `fact` print karein.
- **Expected Output:**

```text
120
```

**Question 10: Star Line**

- **Scenario:** Ek teacher bachon ko pattern sikhana chahti hai. Har line mein pichli line se ek sitara zyada hona chahiye.
- **Given:** `var line = "";`
- **Task:** `for` loop mein `i` ko `1` se `5` tak chalayein. Har chakkar mein `line = line + "*";` karein aur phir `line` print karein.
- **Expected Output:**

```text
*
**
***
****
*****
```

**Question 11: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
for (var i = 0; i < 3; i++) {
  console.log("Hello " + i);
}
```

- **Task:** Output kya hoga? Dry run table bana kar batayein.
- **Expected Output:**

```text
Hello 0
Hello 1
Hello 2
```

### Section B: Array ke sath `for` Loop

**Question 12: Student List**

- **Scenario:** Class teacher ko attendance sheet par har student ka naam alag line mein dikhana hai.
- **Given:** `var students = ["Ayesha", "Sana", "Hira", "Noor"];`
- **Task:** `for` loop se saare naam print karein.
- **Expected Output:**

```text
Ayesha
Sana
Hira
Noor
```

**Question 13: Total Marks**

- **Scenario:** Ek teacher ko 5 students ke marks ka total nikalna hai.
- **Given:** `var marks = [78, 85, 62, 90, 55];`
- **Task:** `for` loop se saare marks ka total nikal kar print karein.
- **Expected Output:**

```text
370
```

**Question 14: Class Average**

- **Scenario:** Principal ko class ka average marks dekhna hai.
- **Given:** `var marks = [78, 85, 62, 90, 55];`
- **Task:** Total nikalein, phir `total / marks.length` se average print karein.
- **Expected Output:**

```text
74
```

**Question 15: Shopping Bill**

- **Scenario:** Hira ne ek dukan se 4 cheezein khareedi hain aur cashier ko poora bill banana hai.
- **Given:** `var prices = [250, 400, 150, 300];`
- **Task:** `for` loop se saari qeematon ka total bill nikal kar print karein.
- **Expected Output:**

```text
1100
```

**Question 16: Topper Marks**

- **Scenario:** School ko sab se zyada marks wale student ke marks announce karne hain.
- **Given:** `var marks = [45, 82, 67, 91, 58];`
- **Task:** `for` loop aur `if` se sab se zyada marks (highest) dhoondh kar print karein.
- **Expected Output:**

```text
91
```

**Question 17: Passed Students**

- **Scenario:** Ek teacher ko batana hai ke kitne students pass huye. Pass hone ke liye marks 50 ya us se zyada hone chahiye.
- **Given:** `var marks = [45, 72, 38, 66, 90, 49];`
- **Task:** `for` loop aur `if` se pass hone wale students ki tadaad print karein.
- **Expected Output:**

```text
3
```

**Question 18: Reverse Order**

- **Scenario:** Ek app haftay ke dinon ki list ulti tarteeb mein dikhana chahti hai.
- **Given:** `var days = ["Mon", "Tue", "Wed", "Thu"];`
- **Task:** `for` loop se array ko ulta (aakhri se pehli value tak) print karein.
- **Expected Output:**

```text
Thu
Wed
Tue
Mon
```

**Question 19: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var nums = [2, 4, 6];
var total = 0;

for (var i = 0; i < nums.length; i++) {
  total = total + nums[i];
  console.log(total);
}
```

- **Task:** Teeno lines ka output likhein aur dry run table se wajah batayein.
- **Expected Output:**

```text
2
6
12
```

### Section C: Debugging Challenge (Ghalti dhundein)

**Question 20: Extra `undefined`**

- **Scenario:** Ek student ne fruits print karne ka code likha, lekin aakhir mein `undefined` bhi print ho raha hai.

```javascript
var fruits = ["Apple", "Banana", "Mango"];

for (var i = 0; i <= fruits.length; i++) {
  console.log(fruits[i]);
}
```

- **Task:** Ghalti dhundein, usay theek karein, aur batayein ke ghalti kyun thi.
- **Hint:** Aakhri index `length - 1` hota hai. Condition mein `<` ya `<=` mein se kaun sa sahi hai?
- **Expected Output (theek code ke baad):**

```text
Apple
Banana
Mango
```

**Question 21: Loop Kabhi Nahi Rukta (Infinite Loop)**

- **Scenario:** Ek student ne 1 se 5 tak ginti print karne ka code likha, lekin browser atak gaya (hang ho gaya).

```javascript
for (var i = 1; i <= 5; i--) {
  console.log(i);
}
```

- **Task:** Ghalti dhundein, usay theek karein, aur batayein ke loop kyun nahi ruk raha tha.
- **Hint:** Condition `i <= 5` hamesha true kyun rehti hai?
- **Expected Output (theek code ke baad):**

```text
1
2
3
4
5
```