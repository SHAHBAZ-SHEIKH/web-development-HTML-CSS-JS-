# JavaScript: Conditional Statements (if, else, else if)

> **Note:** Is lecture mein har example aur har question mein sirf **ek single condition** use ho rahi hai. Multiple conditions (`&&`, `||`) agle lecture mein cover hongi.

---

## Lecture Roadmap

| Step | Topic | Maqsad |
| --- | --- | --- |
| 1 | Decision Making kya hai? | Concept samajhna |
| 2 | `if` statement | Sirf ek raasta |
| 3 | `if ... else` | Do raaste |
| 4 | `else if` | Kayi raaste |
| 5 | `if / else if / else` | Sab ko mila kar use karna |

---

## Diagram kaise parhein? (Pehle yeh samjhein)

Is lecture ke saare diagrams isi rule par bane hain:

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

| Nishan | Matlab |
| --- | --- |
| **Box** `┌───┐` | Yahan condition **check** hoti hai (sawal puchha jata hai) |
| **`── true ──►`** (right side) | Condition **sahi** nikli, to is raaste par jao |
| **`false` aur `▼`** (neeche) | Condition **ghalat** nikli, to neeche wale step par jao |

**Asaan rule:** Box = sawal. **Right = Haan (true)**. **Neeche = Naa (false)**.

---

## Step 1: Decision Making kya hai?

Hum apni zindagi mein har roz **faislay (decisions)** lete hain:

- **Agar** baarish ho rahi hai, **to** chhatri le jao.
- **Warna** (otherwise) chhatri ki zaroorat nahi.

Programming mein bhi computer ko faislay lene hote hain. JavaScript mein yeh kaam **Conditional Statements** karte hain.

**Conditional Statement ka matlab:** Computer pehle ek **condition check** karta hai. Condition **true** ho to ek kaam karta hai, **false** ho to doosra kaam (ya kuch nahi).

### Yaad rakhein: Condition hamesha true ya false hoti hai

```javascript
var marks = 70;

console.log(marks >= 50);   // true
console.log(marks >= 90);   // false
```

Pichle lecture mein humne **Comparison Operators** (`>`, `<`, `>=`, `<=`, `===`) seekhe the. Yahi operators conditions banane ke liye use hote hain.

---

## Step 2: `if` Statement

### Real life example

> **Agar** aap ki attendance 75% ya us se zyada hai, **to** aap exam mein baith sakti hain.

Yahan sirf ek hi kaam hai: condition sahi ho to kaam hoga, warna kuch nahi hoga.

### Pseudo Code

Pseudo code asal code nahi hota, yeh aam zubaan mein steps likhne ka tareeqa hai taake logic samajh aaye.

```text
START
  attendance ki value lo
  IF attendance >= 75 THEN
      "You can sit in the exam" dikhao
  END IF
END
```

### Diagram

```
   START
     │
     ▼
┌────────────────────┐
│ attendance >= 75 ? │── true ──►  Print "You can sit in the exam"
└────────────────────┘
     │
   false
     │
     ▼
 Kuch nahi hoga (if block skip), program aage barh jayega
```

### JavaScript Syntax

```javascript
if (condition) {
  // Yeh code tab chalega jab condition TRUE ho
}
```

| Hissa | Matlab |
| --- | --- |
| `if` | Keyword: "agar" |
| `( )` | Brackets, jin ke andar **condition** likhte hain |
| `{ }` | Curly braces, jin ke andar woh **code** likhte hain jo condition true hone par chalega |

### Example 1

```javascript
var attendance = 80;

if (attendance >= 75) {
  console.log("You can sit in the exam");
}
```

**Output:**

```text
You can sit in the exam
```

### Step by step execution (kaise kaam karta hai)

1. JavaScript `attendance = 80` store karti hai.
2. `if` mein condition check hoti hai: `80 >= 75`.
3. Result **true** aata hai.
4. Curly braces `{ }` ke andar wala code chal jata hai.

### Agar condition false ho to?

```javascript
var attendance = 60;

if (attendance >= 75) {
  console.log("You can sit in the exam");
}

console.log("Program finished");
```

**Output:**

```text
Program finished
```

Condition `60 >= 75` **false** hai, is liye `if` ka block **skip** ho gaya. Sirf `if` ke bahar wali line chali.

### Example 2: Weather

```javascript
var temperature = 38;

if (temperature > 35) {
  console.log("It is very hot. Drink water!");
}
```

### Example 3: Shopping

```javascript
var walletAmount = 1500;

if (walletAmount >= 1000) {
  console.log("You can buy the dress");
}
```

### Common Mistakes (aam ghaltiyan)

| Ghalat | Sahi | Wajah |
| --- | --- | --- |
| `if (marks = 50)` | `if (marks === 50)` | `=` value assign karta hai, muqabla nahi karta |
| `If (marks > 50)` | `if (marks > 50)` | JavaScript **case-sensitive** hai, `if` chhote letters mein likhein |
| `if marks > 50 { }` | `if (marks > 50) { }` | Condition brackets `( )` ke andar honi chahiye |

### Practice Questions: `if` (Students ke liye)

**Question 1: Age Check**

- **Scenario:** Ayesha ki age 20 saal hai. Program ko check karna hai ke woh adult hai ya nahi.
- **Given:** `var age = 20;`
- **Task:** Agar `age` ki value `18` ya us se zyada hai to console mein `You are an adult` print karein.
- **Expected Output:** `You are an adult`

**Question 2: Exam Result**

- **Scenario:** Fatima ne exam diya hai aur uske marks 65 aaye hain. Pass hone ke liye marks 50 se zyada hone chahiye.
- **Given:** `var marks = 65;`
- **Task:** Agar `marks` ki value `50` se zyada hai to console mein `You passed the exam` print karein.
- **Expected Output:** `You passed the exam`

**Question 3: ATM Machine**

- **Scenario:** Maryam ke bank account mein 5000 rupay hain. ATM sirf tab paise nikalne deta hai jab balance 1000 se zyada ho.
- **Given:** `var balance = 5000;`
- **Task:** Agar `balance` ki value `1000` se zyada hai to console mein `You can withdraw money` print karein.
- **Expected Output:** `You can withdraw money`

**Question 4: Jacket Reminder**

- **Scenario:** Aaj ka temperature 15 degree hai. Jab temperature 20 se kam ho to jacket pehenna chahiye.
- **Given:** `var temperature = 15;`
- **Task:** Agar `temperature` ki value `20` se kam hai to console mein `Wear a jacket` print karein.
- **Expected Output:** `Wear a jacket`

**Bonus Question: Think and Explain**

- **Scenario:** Question 2 mein Fatima ke marks 65 ki jagah sirf 40 hain.
- **Task:** Code mein `var marks = 40;` likh kar run karein. Kya output aaya? Aisa kyun hua? Apne alfaaz mein explain karein.
- **Expected Answer:** Kuch bhi print nahi hoga, kyun ke condition `40 > 50` **false** hai aur `if` ka block skip ho jata hai.

---

## Step 3: `if ... else` Statement

### Masla (Problem)

`if` sirf **true** hone par kaam karta hai. Agar condition **false** ho to kuch bhi nahi hota. Lekin real life mein aksar hamein **dono surtoon (cases)** mein kuch na kuch karna hota hai.

### Real life example

> **Agar** aap ke marks 50 ya zyada hain, **to** "Pass". **Warna** "Fail".

Yahan do raaste hain, aur ek raasta zaroor chalega.

### Pseudo Code

```text
START
  marks ki value lo
  IF marks >= 50 THEN
      "Pass" dikhao
  ELSE
      "Fail" dikhao
  END IF
END
```

### Diagram

```
   START
     │
     ▼
┌───────────────┐
│ marks >= 50 ? │── true ──►  Print "Pass"
└───────────────┘
     │
   false
     │
     ▼
 Print "Fail"
```

**Dhyan dein:** Dono mein se **sirf ek** kaam hota hai, kabhi dono ek sath nahi.

### JavaScript Syntax

```javascript
if (condition) {
  // Condition TRUE ho to yeh chalega
} else {
  // Condition FALSE ho to yeh chalega
}
```

### Example 1: Pass or Fail

```javascript
var marks = 45;

if (marks >= 50) {
  console.log("Pass");
} else {
  console.log("Fail");
}
```

**Output:**

```text
Fail
```

**Explanation:** `45 >= 50` false hai, is liye `else` ka block chala.

### Example 2: Voting Eligibility

```javascript
var age = 17;

if (age >= 18) {
  console.log("You can vote");
} else {
  console.log("You cannot vote yet");
}
```

### Example 3: Even ya Odd number

```javascript
var number = 7;

if (number % 2 === 0) {
  console.log("Even number");
} else {
  console.log("Odd number");
}
```

**Tip:** `%` (modulus) baqi (remainder) deta hai. Agar kisi number ko 2 se taqseem karne par baqi `0` bache to woh **even** hai.

### Problem Questions: `if ... else` (Students ke liye)

**Problem 1: Pass or Fail**

- **Scenario:** Zainab ke exam mein 72 marks aaye hain. Pass hone ke liye kam az kam 50 marks chahiye.
- **Given:** `var marks = 72;`
- **Task:** Agar `marks` ki value `50` ya us se zyada hai to `Pass` print karein, warna `Fail` print karein.
- **Expected Output:** `Pass`

**Problem 2: Shopping Discount**

- **Scenario:** Ek clothing store par Hira ka bill 3000 rupay bana hai. Store ka rule hai ke 2000 rupay se zyada ke bill par discount milta hai.
- **Given:** `var billAmount = 3000;`
- **Task:** Agar `billAmount` ki value `2000` se zyada hai to `Discount available` print karein, warna `No discount` print karein.
- **Expected Output:** `Discount available`

**Problem 3: CNIC Eligibility**

- **Scenario:** Sana ki age 16 saal hai. CNIC banwane ke liye age 18 saal ya us se zyada honi chahiye.
- **Given:** `var age = 16;`
- **Task:** Agar `age` ki value `18` ya us se zyada hai to `Eligible for CNIC` print karein, warna `Not eligible yet` print karein.
- **Expected Output:** `Not eligible yet`

**Problem 4: Even or Odd**

- **Scenario:** Teacher ne ek number diya hai aur students ko batana hai ke woh even hai ya odd.
- **Given:** `var number = 10;`
- **Task:** Agar `number % 2 === 0` hai to `Even number` print karein, warna `Odd number` print karein.
- **Expected Output:** `Even number`

**Problem 5: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var temperature = 25;

if (temperature > 30) {
  console.log("Hot day");
} else {
  console.log("Pleasant day");
}
```

- **Task:** Code run kiye baghair batayein ke output kya hoga aur kyun.
- **Expected Output:** `Pleasant day` (kyun ke `25 > 30` false hai).

---

## Step 4: `else if` Statement

### Masla (Problem): Do se zyada raaste

`if ... else` sirf **do** raaste deta hai. Lekin kabhi kabhi hamein **kayi options** chahiye hote hain.

**Real life example: Grade system**

| Marks | Grade |
| --- | --- |
| 80 ya zyada | A |
| 60 ya zyada | B |
| 40 ya zyada | C |
| Is se kam | Fail |

Yahan chaar raaste hain, is liye sirf `if ... else` kafi nahi. Isi liye hum **`else if`** use karte hain.

### `else if` kyun use karte hain?

- Jab **do se zyada** options (cases) hon.
- Jab ek ke baad ek condition **order mein** check karni ho.
- Code saaf (clean) aur samajhne mein asaan rehta hai.

### `else if` kaise kaam karta hai?

JavaScript conditions ko **upar se neeche (top to bottom)** check karti hai. Jo condition sab se pehle **true** ho jaye, uska block chal kar baqi sab conditions **skip** ho jati hain.

### Pseudo Code

```text
START
  marks ki value lo
  IF marks >= 80 THEN
      Grade "A"
  ELSE IF marks >= 60 THEN
      Grade "B"
  ELSE IF marks >= 40 THEN
      Grade "C"
  ELSE
      "Fail"
  END IF
END
```

### Diagram 1: General Structure

```
┌─────────────┐
│ condition1? │── true ──►  Task A
└─────────────┘
   │
 false
   │
   ▼
┌─────────────┐
│ condition2? │── true ──►  Task B
└─────────────┘
   │
 false
   │
   ▼
┌─────────────┐
│ condition3? │── true ──►  Task C
└─────────────┘
   │
 false
   │
   ▼
 Task D  (yeh `else` hai, jab upar ki koi bhi condition true na ho)
```

**Yaad rakhein:** Jaise hi koi condition **true** hoti hai, us ka task chal kar program wahin ruk jata hai. Neeche wali conditions check hi nahi hoti.

### Diagram 2: Grade System (marks = 65)

```
┌───────────────┐
│ marks >= 80 ? │── true ──►  Grade A
└───────────────┘
   │
 false   (65 >= 80 ghalat hai)
   │
   ▼
┌───────────────┐
│ marks >= 60 ? │── true ──►  Grade B   ◄── yahan true mila, program yahin ruk gaya
└───────────────┘
   │
 false
   │
   ▼
┌───────────────┐
│ marks >= 40 ? │── true ──►  Grade C
└───────────────┘
   │
 false
   │
   ▼
 Fail
```

### JavaScript Syntax

```javascript
if (condition1) {
  // condition1 true ho to yeh chalega
} else if (condition2) {
  // condition1 false aur condition2 true ho to yeh chalega
} else if (condition3) {
  // condition3 true ho to yeh chalega
} else {
  // upar ki koi bhi condition true na ho to yeh chalega
}
```

### Example 1: Grade System

```javascript
var marks = 65;

if (marks >= 80) {
  console.log("Grade A");
} else if (marks >= 60) {
  console.log("Grade B");
} else if (marks >= 40) {
  console.log("Grade C");
} else {
  console.log("Fail");
}
```

**Output:**

```text
Grade B
```

### Step by step execution (marks = 65)

| Step | Condition | Result | Action |
| --- | --- | --- | --- |
| 1 | `65 >= 80` | false | Aage jao |
| 2 | `65 >= 60` | **true** | `Grade B` print, **baqi sab skip** |
| 3 | `65 >= 40` | (check nahi hui) | Skip |

### Example 2: Traffic Light

```javascript
var light = "yellow";

if (light === "red") {
  console.log("Stop");
} else if (light === "yellow") {
  console.log("Get ready");
} else if (light === "green") {
  console.log("Go");
} else {
  console.log("Invalid light colour");
}
```

### Example 3: Temperature Message

```javascript
var temperature = 28;

if (temperature >= 40) {
  console.log("Extreme heat");
} else if (temperature >= 30) {
  console.log("Hot");
} else if (temperature >= 20) {
  console.log("Pleasant");
} else {
  console.log("Cold");
}
```

### Order ki ahmiyat (Important Concept)

Conditions ka **order** bohat zaroori hai. Is example ko dekhein:

```javascript
var marks = 85;

// Ghalat order
if (marks >= 40) {
  console.log("Grade C");
} else if (marks >= 60) {
  console.log("Grade B");
} else if (marks >= 80) {
  console.log("Grade A");
}
```

**Output:** `Grade C`, jo ghalat hai, kyun ke `85 >= 40` sab se pehle true ho gayi aur baqi conditions check hi nahi hui.

**Rule:** Hamesha **sab se bari (strict) condition pehle** likhein, phir kam strict.

### Practice Questions: `else if` (Students ke liye)

**Question 1: Grade Calculator**

- **Scenario:** Ek school mein result card ke liye marks ke hisaab se grade dena hai. Areeba ke marks 55 hain.
- **Given:** `var marks = 55;`
- **Task:** Neeche diye gaye rules ke mutabiq grade print karein.

| Marks | Print karein |
| --- | --- |
| `80` ya zyada | `Grade A` |
| `60` ya zyada | `Grade B` |
| `40` ya zyada | `Grade C` |
| Is se kam | `Fail` |

- **Expected Output:** `Grade C`

**Question 2: Weather Report**

- **Scenario:** Weather app aaj ke temperature ke hisaab se message dikhati hai. Aaj ka temperature 33 degree hai.
- **Given:** `var temperature = 33;`
- **Task:** Neeche diye gaye rules ke mutabiq message print karein.

| Temperature | Print karein |
| --- | --- |
| `35` se zyada | `Very hot` |
| `25` se zyada | `Warm` |
| `15` se zyada | `Cool` |
| Is se kam ya barabar | `Cold` |

- **Expected Output:** `Warm`

**Question 3: Day Message**

- **Scenario:** Ek planner app din ke naam ke hisaab se message dikhati hai. Aaj ka din Friday hai.
- **Given:** `var day = "Friday";`
- **Task:** Neeche diye gaye rules ke mutabiq message print karein (`===` use karein).

| Agar day yeh ho | Print karein |
| --- | --- |
| `"Saturday"` | `Weekend` |
| `"Friday"` | `Almost weekend` |
| `"Monday"` | `Start of the week` |
| Koi aur din | `Normal day` |

- **Expected Output:** `Almost weekend`

**Question 4: Predict the Output (Bina run kiye batayein)**

- **Scenario:** Neeche diye gaye code ko dhyan se parhein.

```javascript
var score = 50;

if (score >= 90) {
  console.log("Excellent");
} else if (score >= 70) {
  console.log("Good");
} else if (score >= 50) {
  console.log("Average");
} else {
  console.log("Poor");
}
```

- **Task:** Output kya hoga? Step by step explain karein ke kaun si condition true hui.
- **Expected Output:** `Average` (kyun ke `50 >= 90` false, `50 >= 70` false, `50 >= 50` **true**).

---

## Step 5: `if / else if / else` (Complete Problem Solving)

### Teeno ka khulasa (Summary)

| Statement | Kab use karein | Kitne raaste |
| --- | --- | --- |
| `if` | Sirf ek condition par ek kaam | 1 |
| `if ... else` | Do surtein (true ya false) | 2 |
| `if ... else if ... else` | Kayi options (3 ya zyada) | 3 ya zyada |

### Quick Rules (Yaad rakhne wali baatein)

1. `if` hamesha **sab se pehle** aata hai.
2. `else if` aur `else` hamesha `if` ke **baad** aate hain.
3. `else` ke sath **condition nahi** likhte.
4. `else if` kitne bhi ho sakte hain, lekin `if` aur `else` sirf **ek ek** dafa.
5. Sirf **ek block** execute hota hai (jo pehle true ho).
6. Condition ke liye `===` use karein, `=` nahi.

### Complete Example: Online Shopping Discount

```javascript
var totalBill = 7500;

if (totalBill >= 10000) {
  console.log("30% discount");
} else if (totalBill >= 5000) {
  console.log("20% discount");
} else if (totalBill >= 2000) {
  console.log("10% discount");
} else {
  console.log("No discount");
}
```

**Output:**

```text
20% discount
```

### Diagram (totalBill = 7500)

```
┌──────────────────────┐
│ totalBill >= 10000 ? │── true ──►  30% discount
└──────────────────────┘
   │
 false   (7500 >= 10000 ghalat hai)
   │
   ▼
┌─────────────────────┐
│ totalBill >= 5000 ? │── true ──►  20% discount   ◄── yahan true mila, program yahin ruk gaya
└─────────────────────┘
   │
 false
   │
   ▼
┌─────────────────────┐
│ totalBill >= 2000 ? │── true ──►  10% discount
└─────────────────────┘
   │
 false
   │
   ▼
 No discount
```

### Final Problem Questions (Students ke liye)

**Problem 1: Result System**

- **Scenario:** Ek college mein final result ke marks ke hisaab se remarks diye jate hain. Rida ke marks 78 hain.
- **Given:** `var marks = 78;`
- **Task:** Neeche diye gaye rules ke mutabiq remarks print karein.

| Marks | Print karein |
| --- | --- |
| `90` ya zyada | `Outstanding` |
| `75` ya zyada | `Very Good` |
| `50` ya zyada | `Good` |
| Is se kam | `Needs improvement` |

- **Expected Output:** `Very Good`

**Problem 2: Mobile Battery**

- **Scenario:** Ek mobile phone battery percentage ke hisaab se message dikhata hai. Aaj Sidra ke phone ki battery 35 percent hai.
- **Given:** `var battery = 35;`
- **Task:** Neeche diye gaye rules ke mutabiq message print karein.

| Battery | Print karein |
| --- | --- |
| `80` se zyada | `Battery is full` |
| `50` se zyada | `Battery is okay` |
| `20` se zyada | `Battery is low` |
| Is se kam ya barabar | `Please charge your phone` |

- **Expected Output:** `Battery is low`

**Problem 3: Library Fine**

- **Scenario:** College library mein kitab late wapas karne par fine lagta hai. Hania ne kitab 6 din late wapas ki hai.
- **Given:** `var lateDays = 6;`
- **Task:** Neeche diye gaye rules ke mutabiq fine print karein.

| Late Days | Print karein |
| --- | --- |
| `15` se zyada | `Fine: Rs. 500` |
| `7` se zyada | `Fine: Rs. 200` |
| `0` se zyada | `Fine: Rs. 50` |
| Is se kam ya barabar | `No fine` |

- **Expected Output:** `Fine: Rs. 50`

**Problem 4: Age Category**

- **Scenario:** Ek survey form mein age ke hisaab se category likhni hai. Noor ki age 14 saal hai.
- **Given:** `var age = 14;`
- **Task:** Neeche diye gaye rules ke mutabiq category print karein.

| Age | Print karein |
| --- | --- |
| `60` ya zyada | `Senior citizen` |
| `18` ya zyada | `Adult` |
| `13` ya zyada | `Teenager` |
| Is se kam | `Child` |

- **Expected Output:** `Teenager`

**Problem 5: Speed Check**

- **Scenario:** Motorway par speed camera gaari ki speed check karta hai. Ek gaari 65 km/h par chal rahi hai.
- **Given:** `var speed = 65;`
- **Task:** Neeche diye gaye rules ke mutabiq message print karein.

| Speed | Print karein |
| --- | --- |
| `100` se zyada | `Danger: Too fast` |
| `80` se zyada | `Warning: Slow down` |
| `40` se zyada | `Normal speed` |
| Is se kam ya barabar | `Very slow` |

- **Expected Output:** `Normal speed`

**Challenge Question: Debugging (Ghalti dhundein)**

- **Scenario:** Ek student ne marks ke hisaab se grade dene wala code likha, lekin 90 marks par bhi ghalat grade aa raha hai.

```javascript
var marks = 90;

if (marks >= 40) {
  console.log("Grade C");
} else if (marks >= 60) {
  console.log("Grade B");
} else if (marks >= 80) {
  console.log("Grade A");
}
```

- **Task:** Code ki ghalti dhundein, usay theek karein, aur batayein ke ghalti kyun thi.
- **Hint:** Conditions ka order dekhein.
- **Expected Output (theek code ke baad):** `Grade A`

---

## Final Revision

| Concept | Yaad rakhein |
| --- | --- |
| Condition | Hamesha `true` ya `false` result deti hai |
| `if` | Condition true ho to code chalta hai |
| `else` | Condition false ho to code chalta hai (condition nahi likhte) |
| `else if` | Do se zyada options ke liye |
| Order | Conditions upar se neeche check hoti hain |
| Execution | Sirf **ek** block chalta hai |
| Comparison | `===` use karein, `=` nahi |

---

## Teacher Solutions (Answer Key)

### `if` Questions

```javascript
// Question 1
var age = 20;
if (age >= 18) {
  console.log("You are an adult");
}

// Question 2
var marks = 65;
if (marks > 50) {
  console.log("You passed the exam");
}

// Question 3
var balance = 5000;
if (balance > 1000) {
  console.log("You can withdraw money");
}

// Question 4
var temperature = 15;
if (temperature < 20) {
  console.log("Wear a jacket");
}
```

### `if ... else` Problems

```javascript
// Problem 1
var marks = 72;
if (marks >= 50) {
  console.log("Pass");
} else {
  console.log("Fail");
}

// Problem 2
var billAmount = 3000;
if (billAmount > 2000) {
  console.log("Discount available");
} else {
  console.log("No discount");
}

// Problem 3
var age = 16;
if (age >= 18) {
  console.log("Eligible for CNIC");
} else {
  console.log("Not eligible yet");
}

// Problem 4
var number = 10;
if (number % 2 === 0) {
  console.log("Even number");
} else {
  console.log("Odd number");
}
```

Problem 5 ka answer: `Pleasant day`.

### `else if` Questions

```javascript
// Question 1
var marks = 55;
if (marks >= 80) {
  console.log("Grade A");
} else if (marks >= 60) {
  console.log("Grade B");
} else if (marks >= 40) {
  console.log("Grade C");
} else {
  console.log("Fail");
}

// Question 2
var temperature = 33;
if (temperature > 35) {
  console.log("Very hot");
} else if (temperature > 25) {
  console.log("Warm");
} else if (temperature > 15) {
  console.log("Cool");
} else {
  console.log("Cold");
}

// Question 3
var day = "Friday";
if (day === "Saturday") {
  console.log("Weekend");
} else if (day === "Friday") {
  console.log("Almost weekend");
} else if (day === "Monday") {
  console.log("Start of the week");
} else {
  console.log("Normal day");
}
```

Question 4 ka answer: `Average`.

### Final Problems

```javascript
// Problem 1
var marks = 78;
if (marks >= 90) {
  console.log("Outstanding");
} else if (marks >= 75) {
  console.log("Very Good");
} else if (marks >= 50) {
  console.log("Good");
} else {
  console.log("Needs improvement");
}

// Problem 2
var battery = 35;
if (battery > 80) {
  console.log("Battery is full");
} else if (battery > 50) {
  console.log("Battery is okay");
} else if (battery > 20) {
  console.log("Battery is low");
} else {
  console.log("Please charge your phone");
}

// Problem 3
var lateDays = 6;
if (lateDays > 15) {
  console.log("Fine: Rs. 500");
} else if (lateDays > 7) {
  console.log("Fine: Rs. 200");
} else if (lateDays > 0) {
  console.log("Fine: Rs. 50");
} else {
  console.log("No fine");
}

// Problem 4
var age = 14;
if (age >= 60) {
  console.log("Senior citizen");
} else if (age >= 18) {
  console.log("Adult");
} else if (age >= 13) {
  console.log("Teenager");
} else {
  console.log("Child");
}

// Problem 5
var speed = 65;
if (speed > 100) {
  console.log("Danger: Too fast");
} else if (speed > 80) {
  console.log("Warning: Slow down");
} else if (speed > 40) {
  console.log("Normal speed");
} else {
  console.log("Very slow");
}
```

### Debugging Challenge (Theek code)

```javascript
var marks = 90;

if (marks >= 80) {
  console.log("Grade A");
} else if (marks >= 60) {
  console.log("Grade B");
} else if (marks >= 40) {
  console.log("Grade C");
}
```

**Wajah:** Pehle code mein sab se choti condition (`>= 40`) sab se upar thi, is liye `90` bhi wahin true ho gaya. Theek code mein **sab se bari condition pehle** rakhi gayi hai.