# CSS Selectors Guide

**Topics covered:** Class, ID, Child, Descendant, Adjacent Sibling, General Sibling

Yeh guide students ke liye hai. Har selector ko definition, syntax, real-life analogy aur **3 practical examples** ke sath explain kiya gaya hai.

---

## Table of Contents

1. [Basic Terminology](#1-basic-terminology)
2. [Class Selector](#2-class-selector-)
3. [ID Selector](#3-id-selector-)
4. [Child Selector](#4-child-selector-)
5. [Descendant Selector](#5-descendant-selector-space)
6. [Adjacent Sibling Selector](#6-adjacent-sibling-selector-)
7. [General Sibling Selector](#7-general-sibling-selector-)
8. [Quick Comparison Table](#8-quick-comparison-table)
9. [Practice Tasks](#9-practice-tasks)
10. [Complete Practice Code](#10-complete-practice-code)

---

## What is a Selector?

CSS mein **selector** wo pattern hota hai jis ke zariye hum HTML ke specific element(s) ko **target** karte hain, taake un par styling (color, font, spacing waghera) apply ki ja sake.

> **Analogy:** Teacher class mein announcement karti hai: *"Jo students prefect hain, woh stage par aayen."* Yahan teacher ne ek specific group ko target kiya. CSS selector bhi isi tarah elements ko target karta hai.

---

## 1. Basic Terminology

Selectors samajhne se pehle in terms ko samajhna zaroori hai. Yeh sab **DOM tree** (HTML elements ka hierarchical structure) se related hain.

| Term | Definition | Example |
|------|------------|---------|
| **Parent Element** | Wo element jo kisi dusre element ko directly contain kare | `<div>` jis ke andar `<p>` ho, to `div` parent hai |
| **Child Element** | Wo element jo parent ke **bilkul andar (ek level)** ho | `<div>` ke andar directly likha `<p>` |
| **Ancestor Element** | Parent, aur parent ka parent, yaani upar ke sab levels | `<body>` aur `<div>` dono `<p>` ke ancestors ho sakte hain |
| **Descendant Element** | Kisi element ke andar **kisi bhi level** par nested element | `<div>` ke andar `<p>`, ya `<div><div><p>` |
| **Sibling Elements** | Wo elements jin ka **parent same** ho aur same level par hon | Ek `<div>` ke andar do `<p>` tags |
| **Nested Element** | Kisi dusre element ke andar likha hua element | `<ul><li>` mein `li` nested hai |

### Visual Representation (DOM Tree)

```
<div class="school">            <-- Parent of (class-1, class-2)
    <div class="class-1">       <-- Child of school | Sibling of class-2
        <p>Hina</p>             <-- Child of class-1 | Descendant of school
    </div>
    <div class="class-2">       <-- Child of school | Sibling of class-1
        <p>Sara</p>             <-- Child of class-2 | Descendant of school
    </div>
</div>
```

---

## 2. Class Selector (`.`)

### Definition
Class selector un **tamam elements** ko target karta hai jin ke `class` attribute ki value same ho. Ek class **multiple elements** par reuse ki ja sakti hai. Syntax mein **dot (`.`)** use hota hai.

### Real-Life Analogy
School mein bohat si girls **"Prefect"** hoti hain. "Prefect" ek **category (label)** hai jo multiple students ko assign ho sakti hai. Class bhi ek reusable label hai.

### Syntax
```css
.className {
  property: value;
}
```

### Example 1: Prefect Students

```html
<p class="prefect">Ayesha</p>
<p>Fatima</p>
<p class="prefect">Zainab</p>
```

```css
.prefect {
  color: white;
  background-color: green;
  padding: 5px;
}
```

**Output:** Sirf Ayesha aur Zainab par green background apply hoga, kyunke dono ki class `prefect` hai.

---

### Example 2: Topper Students

```html
<div class="topper">Sara - 95%</div>
<div class="topper">Hina - 93%</div>
<div>Maryam - 70%</div>
```

```css
.topper {
  color: goldenrod;
  font-weight: bold;
  border: 2px solid goldenrod;
}
```

**Output:** Sara aur Hina ke records bold text aur golden border ke sath show honge.

---

### Example 3: Sports Team Members

```html
<li class="cricket-team">Noor</li>
<li class="cricket-team">Iqra</li>
<li>Laiba</li>
<li class="cricket-team">Aliza</li>
```

```css
.cricket-team {
  color: blue;
  text-decoration: underline;
}
```

**Output:** Noor, Iqra aur Aliza ke naam blue aur underlined honge.

---

## 3. ID Selector (`#`)

### Definition
ID selector **sirf ek unique element** ko target karta hai. Ek HTML page mein ek ID **sirf ek dafa** use honi chahiye. Syntax mein **hash (`#`)** use hota hai.

### Real-Life Analogy
Aap ka **CNIC number** ya **Roll Number** unique hota hai, kisi aur ke sath share nahi hota. ID bhi ek **unique identifier** hai.

### Syntax
```css
#idName {
  property: value;
}
```

### Example 1: Class Monitor

```html
<p id="monitor">Ayesha (Class Monitor)</p>
<p>Fatima</p>
<p>Zainab</p>
```

```css
#monitor {
  color: red;
  font-size: 24px;
  font-weight: bold;
}
```

**Output:** Class Monitor sirf ek hoti hai, is liye sirf Ayesha ka element highlight hoga.

---

### Example 2: Head Girl

```html
<h2 id="head-girl">Sara - Head Girl</h2>
<h3>Hina - Student</h3>
```

```css
#head-girl {
  background-color: purple;
  color: white;
  padding: 10px;
}
```

**Output:** Head Girl ek unique position hai, is liye `#head-girl` sirf us element ko target karega.

---

### Example 3: Principal

```html
<div id="principal">Madam Nasreen (Principal)</div>
<div>Miss Rabia (Teacher)</div>
```

```css
#principal {
  border: 3px solid black;
  font-size: 22px;
  background-color: yellow;
}
```

**Output:** Principal sirf ek hoti hai, is liye style sirf us element par apply hogi.

---

### Class vs ID (Important Difference)

| Feature | Class | ID |
|---------|-------|----|
| Symbol | `.` | `#` |
| Reusability | Multiple elements par | Page mein sirf ek element par |
| Purpose | Elements ke group ko style karna | Single unique element ko target karna |
| Specificity | Kam | Zyada (higher priority) |

---

## 4. Child Selector (`>`)

### Definition
Child selector sirf us element ko target karta hai jo specified parent ka **direct child** ho, yaani parent ke **bilkul andar, sirf ek level neeche**. Deeper nested elements select nahi hote. Syntax mein **greater-than sign (`>`)** use hota hai.

### Real-Life Analogy
Ek **Department** mein jo employees **directly Manager ko report** karte hain, wo uske direct reports hain. Un employees ke neeche kaam karne wale log Manager ke direct reports nahi hote. Child selector sirf direct reports ko target karta hai.

```
Manager (div)
 ├── Employee 1 (p)          <-- Direct Child  (selected)
 ├── Employee 2 (p)          <-- Direct Child  (selected)
 └── Team Lead (div)
        └── Intern (p)       <-- NOT a direct child (not selected)
```

### Syntax
```css
parent > child {
  property: value;
}
```

### Example 1: Class Representatives

```html
<div class="classroom">
  <p>Ayesha</p>
  <p>Fatima</p>
  <div class="back-bench">
    <p>Zara</p>
  </div>
</div>
```

```css
.classroom > p {
  color: deeppink;
  font-weight: bold;
}
```

**Output:** Sirf Ayesha aur Fatima style hongi. Zara `back-bench` ke andar nested hai, is liye `.classroom` ki direct child nahi.

---

### Example 2: Seating Arrangement

```html
<div class="hall">
  <span>Hina</span>
  <span>Sara</span>
  <div class="row-2">
    <span>Noor</span>
  </div>
</div>
```

```css
.hall > span {
  color: green;
}
```

**Output:** Hina aur Sara green hongi. Noor nested element hai, is liye select nahi hogi.

---

### Example 3: Navigation Menu

```html
<ul class="menu">
  <li>Home</li>
  <li>About
    <ul>
      <li>Our Team</li>
    </ul>
  </li>
  <li>Contact</li>
</ul>
```

```css
.menu > li {
  background-color: lightblue;
  padding: 5px;
}
```

**Output:** Home, About aur Contact par style apply hogi. "Our Team" nested list ka item hai, is liye select nahi hoga.

---

## 5. Descendant Selector (space)

### Definition
Descendant selector kisi ancestor element ke andar maujood **tamam nested elements** ko target karta hai, chahe woh **direct child hon ya kisi bhi deeper level par**. Syntax mein **space (` `)** use hota hai.

### Real-Life Analogy
Ek **Company** ke andar jitne bhi employees hain, chahe woh directly CEO ko report karte hon ya kai levels neeche hon, sab us company ke members hain. Descendant selector in sab ko cover karta hai.

```
Company (div)
 ├── Manager (p)                 <-- Descendant (selected)
 └── Department (div)
        └── Employee (p)         <-- Descendant (selected)
              └── Intern (p)     <-- Descendant (selected)
```

### Syntax
```css
ancestor descendant {
  property: value;
}
```

### Example 1: Complete Hierarchy

```html
<div class="company">
  <p>Ayesha (Manager)</p>
  <div>
    <p>Zara (Employee)</p>
  </div>
</div>
```

```css
.company p {
  color: purple;
}
```

**Output:** Ayesha aur Zara **dono** purple hongi. (Child selector use hota to sirf Ayesha hoti.)

---

### Example 2: School Structure

```html
<div class="school">
  <div class="class-1">
    <p>Hina</p>
  </div>
  <div class="class-2">
    <p>Sara</p>
    <div class="group">
      <p>Noor</p>
    </div>
  </div>
</div>
```

```css
.school p {
  font-size: 20px;
  color: darkblue;
}
```

**Output:** Hina, Sara aur Noor **tino** select hongi, chahe woh kitne bhi levels andar nested hon.

---

### Example 3: Links Inside an Article

```html
<article>
  <p>Visit <a href="#">our site</a></p>
  <div>
    <p>Or <a href="#">contact us</a></p>
  </div>
</article>
<a href="#">Outside link</a>
```

```css
article a {
  color: red;
  text-decoration: none;
}
```

**Output:** `article` ke andar ke dono links red honge. `Outside link` article ke bahar hai, is liye affect nahi hoga.

---

### Child vs Descendant (Important Difference)

| Feature | Child Selector (`>`) | Descendant Selector (space) |
|---------|----------------------|------------------------------|
| Targets | Sirf direct children | Tamam nested elements (any level) |
| Depth | Sirf 1 level | Unlimited levels |
| Example | `div > p` | `div p` |

---

## 6. Adjacent Sibling Selector (`+`)

### Definition
Adjacent Sibling selector us element ko target karta hai jo reference element ke **immediately baad (next)** aaye, aur dono ka **parent same** ho. Sirf **ek** element select hota hai. Syntax mein **plus sign (`+`)** use hota hai.

### Real-Life Analogy
Attendance queue mein agar kaha jaye *"Ayesha ke **bilkul peeche** khari student"*, to sirf **ek** student select hoti hai, jo Ayesha ke immediately baad khari hai.

```
Queue:  Ayesha  ->  Fatima  ->  Zainab  ->  Hina
                      ^
          Immediately following sibling (selected)
```

### Syntax
```css
element1 + element2 {
  property: value;
}
```

### Example 1: Student After Ayesha

```html
<p class="ayesha">Ayesha</p>
<p>Fatima</p>
<p>Zainab</p>
<p>Hina</p>
```

```css
.ayesha + p {
  color: red;
  font-weight: bold;
}
```

**Output:** Sirf **Fatima** red hogi (Ayesha ke immediately baad). Zainab aur Hina affect nahi hongi.

---

### Example 2: Paragraph After Heading

```html
<h2>Class Rules</h2>
<p>Time par aao.</p>
<p>Homework complete karo.</p>
```

```css
h2 + p {
  font-size: 20px;
  color: green;
}
```

**Output:** Sirf pehla paragraph ("Time par aao.") green aur bara hoga.

---

### Example 3: Seat Next to Group Leader

```html
<div class="bench">
  <span class="leader">Sara (Leader)</span>
  <span>Noor</span>
  <span>Iqra</span>
</div>
```

```css
.leader + span {
  background-color: yellow;
}
```

**Output:** Sirf **Noor** yellow hogi (Sara ke immediately baad). Iqra select nahi hogi.

---

## 7. General Sibling Selector (`~`)

### Definition
General Sibling selector reference element ke **baad aane wale tamam siblings** ko target karta hai (sirf pehla nahi, **sab**), shart yeh hai ke **parent same ho**. Reference element se **pehle** wale siblings select nahi hote. Syntax mein **tilde (`~`)** use hota hai.

### Real-Life Analogy
Queue mein agar kaha jaye *"Ayesha ke **baad jitni bhi students** hain, sab aage aayen"*, to Ayesha ke baad wali **tamam students** select hongi. Ayesha se pehle wali select nahi hongi.

```
Queue:  Hina  ->  Ayesha  ->  Fatima  ->  Zainab  ->  Sara
                                 ^           ^          ^
                       All following siblings (selected)
```

### Syntax
```css
element1 ~ element2 {
  property: value;
}
```

### Example 1: All Students After Ayesha

```html
<p>Hina</p>
<p class="ayesha">Ayesha</p>
<p>Fatima</p>
<p>Zainab</p>
<p>Sara</p>
```

```css
.ayesha ~ p {
  color: blue;
  font-weight: bold;
}
```

**Output:** Fatima, Zainab aur Sara **teeno** blue hongi. Hina select nahi hogi (kyunke wo Ayesha se pehle hai).

---

### Example 2: All Paragraphs After Heading

```html
<h2>Instructions</h2>
<p>Pehla point</p>
<p>Doosra point</p>
<p>Teesra point</p>
```

```css
h2 ~ p {
  color: darkgreen;
}
```

**Output:** Teeno paragraphs green hongay. (`+` use hota to sirf pehla hota.)

---

### Example 3: Participants After the Winner

```html
<ul>
  <li>Noor (participant)</li>
  <li class="winner">Iqra (Winner)</li>
  <li>Laiba (participant)</li>
  <li>Aliza (participant)</li>
</ul>
```

```css
.winner ~ li {
  opacity: 0.5;
}
```

**Output:** Laiba aur Aliza faded hongi. Noor affect nahi hogi.

---

### Adjacent vs General Sibling (Important Difference)

| Feature | Adjacent Sibling (`+`) | General Sibling (`~`) |
|---------|------------------------|------------------------|
| Targets | Sirf **next ek** sibling | Baad wale **tamam** siblings |
| Example | `h2 + p` | `h2 ~ p` |
| Result | 1 element | Multiple elements |

---

## 8. Quick Comparison Table

| Selector | Symbol | Targets | Analogy |
|----------|--------|---------|---------|
| Class | `.` | Same class wale **tamam** elements | Sab Prefect students |
| ID | `#` | **Sirf ek** unique element | Class Monitor |
| Child | `>` | Sirf **direct children** | Manager ke direct reports |
| Descendant | (space) | Tamam **nested elements** | Company ke tamam employees |
| Adjacent Sibling | `+` | **Immediately next** sibling | Queue mein bilkul peeche wali |
| General Sibling | `~` | Baad wale **tamam** siblings | Queue mein peeche wali sab |

### Yaad Rakhne Ka Aasan Tareeqa

- `.` Dot = **Group** (multiple elements)
- `#` Hash = **Unique** (single element)
- `>` Arrow = **Direct child** only
- ` ` Space = **All descendants**
- `+` Plus = **Only the next** sibling
- `~` Tilde = **All following** siblings

---

## 9. Practice Tasks

1. 5 students ki list banayen. Class selector se 3 students ko pink karein.
2. Class Monitor ko ID selector se red karein.
3. Ek `div` banayen jis mein direct `p` aur ek nested `div` ke andar `p` ho. Child aur Descendant selector ka difference observe karein.
4. Ek list mein `+` aur `~` dono use karein aur dono ka difference note karein.

---

## 10. Complete Practice Code

Neeche complete code hai. Isay `index.html` mein copy karke browser mein open karein:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Selectors Practice</title>
  <style>
    .prefect { color: white; background: green; padding: 3px; }
    #monitor { color: red; font-size: 22px; font-weight: bold; }
    .family > p { color: deeppink; }
    .company p { text-decoration: underline; }
    .ayesha + p { background: yellow; }
    .ayesha ~ span { color: blue; }
  </style>
</head>
<body>

  <h3>Class Selector</h3>
  <p class="prefect">Ayesha</p>
  <p>Fatima</p>
  <p class="prefect">Zainab</p>

  <h3>ID Selector</h3>
  <p id="monitor">Sara (Monitor)</p>

  <h3>Child Selector</h3>
  <div class="family">
    <p>Direct Child</p>
    <div><p>Nested Element</p></div>
  </div>

  <h3>Descendant Selector</h3>
  <div class="company">
    <p>Direct Child</p>
    <div><p>Nested Descendant</p></div>
  </div>

  <h3>Adjacent and General Sibling</h3>
  <div>
    <span>Hina</span>
    <p class="ayesha">Ayesha</p>
    <p>Fatima</p>
    <span>Zainab</span>
    <span>Sara</span>
  </div>

</body>
</html>
```

---

**Happy Learning!** Agar koi sawal ho to class mein pooch lein.
