# CSS Position Property Guide

**Topics covered:** `static`, `relative`, `absolute`, `fixed`, `sticky`, Offset Properties (`top`, `right`, `bottom`, `left`), `z-index`

Yeh guide students ke liye hai. Har position value ko definition, syntax, real-life analogy aur **3 practical examples** ke sath explain kiya gaya hai.

---

## Table of Contents

1. [Position Kya Hai?](#1-position-kya-hai)
2. [Offset Properties](#2-offset-properties-top-right-bottom-left)
3. [position: static](#3-position-static)
4. [position: relative](#4-position-relative)
5. [position: absolute](#5-position-absolute)
6. [position: fixed](#6-position-fixed)
7. [position: sticky](#7-position-sticky)
8. [z-index](#8-z-index)
9. [Quick Comparison Table](#9-quick-comparison-table)
10. [Common Mistakes](#10-common-mistakes)
11. [Practice Tasks](#11-practice-tasks)
12. [Mini Project Ideas](#12-mini-project-ideas)
13. [Complete Practice Code](#13-complete-practice-code)

---

## 1. Position Kya Hai?

### Definition
`position` property decide karti hai ke element page par **kahan aur kis reference ke mutabiq** place hoga. Iske sath hum `top`, `right`, `bottom`, `left` use karke element ko **move** karte hain.

### Normal Flow (Default Behavior)
Browser elements ko **upar se neeche, ek ke baad ek** rakhta hai. Isay **Normal Flow** kehte hain. `position` is flow ko **tod sakti hai** ya us mein **thori tabdeeli** kar sakti hai.

### Real-Life Analogy
Class mein students apni **assigned seats** par baithi hain (yeh Normal Flow hai). Ab:

- Student **apni seat par hi baithi hai** = `static`
- Student apni seat se **thora sa khisak gayi**, lekin us ki purani seat khali rahi = `relative`
- Student ne seat chhor kar **board ke bilkul saamne** khari ho gayi, ab us ki jagah par koi aur baith sakta hai = `absolute`
- Student ko **school gate par permanent guard** bana diya, chahe class kahin bhi chali jaye woh wahin khari rahegi = `fixed`
- Student apni seat par baithi hai, lekin jab **ghar jane ka time aaye** to gate par chipak jaye = `sticky`

### Syntax
```css
selector {
  position: static | relative | absolute | fixed | sticky;
}
```

### Position Values at a Glance

| Value | Normal Flow mein? | Reference (kis se move hoga) |
|-------|-------------------|-------------------------------|
| `static` | Haan | Koi nahi (default) |
| `relative` | Haan (jagah mehfooz rehti hai) | Apni **khud ki original position** |
| `absolute` | **Nahi** (jagah khatam) | Sab se qareeb **positioned parent** |
| `fixed` | **Nahi** (jagah khatam) | **Browser window (viewport)** |
| `sticky` | Haan | Scroll hone par parent ke andar **chipak jata hai** |

---

## 2. Offset Properties (top, right, bottom, left)

### Definition
Yeh properties element ko **kisi reference point se kitna door** rakhna hai yeh batati hain. Yeh sirf tab kaam karti hain jab `position` **`static` ke ilawa koi bhi value** ho.

| Property | Matlab |
|----------|--------|
| `top: 20px` | Reference ke **upar wale kinare se 20px neeche** |
| `bottom: 20px` | Reference ke **neeche wale kinare se 20px upar** |
| `left: 20px` | Reference ke **left kinare se 20px right ki taraf** |
| `right: 20px` | Reference ke **right kinare se 20px left ki taraf** |

> **Yaad rakhne ka tareeqa:** Property ka naam batata hai ke element **kis kinare se** door ho raha hai. `top: 20px` = "upar se 20px door".

### Shortcut: `inset`
```css
.box {
  position: absolute;
  inset: 0;               /* top, right, bottom, left sab 0 (poora parent cover) */
}

.box2 {
  position: absolute;
  inset: 10px 20px;       /* top-bottom 10px | left-right 20px */
}
```

---

## 3. position: static

### Definition
Yeh **default value** hai. Element **Normal Flow** mein rehta hai. `top`, `right`, `bottom`, `left` aur `z-index` is par **kaam nahi karte**.

### Real-Life Analogy
Student apni **assigned seat** par baithi hai. Wahan se hilti nahi.

### Syntax
```css
selector {
  position: static;
}
```

### Example 1: Default Behavior

```html
<p>Pehla paragraph</p>
<p>Doosra paragraph</p>
<p>Teesra paragraph</p>
```

```css
p {
  background-color: lightblue;
  margin: 5px;
}
```

**Output:** Teeno paragraphs upar se neeche order mein aate hain. Humne `position` likha hi nahi, phir bhi yeh `static` hain.

---

### Example 2: Static par Offset Kaam Nahi Karta

```html
<div class="box">Main hilunga?</div>
```

```css
.box {
  position: static;
  top: 50px;
  left: 50px;
  background-color: yellow;
  padding: 10px;
}
```

**Output:** Box **apni jagah se nahi hilega**. `top` aur `left` ignore ho jate hain. Isi liye pehle `position: relative` likhna parta hai.

---

### Example 3: Position Reset Karna

```html
<div class="sidebar">Sidebar</div>
```

```css
.sidebar {
  position: fixed;
  top: 0;
  left: 0;
}

@media (max-width: 600px) {
  .sidebar {
    position: static;   /* Mobile par normal flow mein wapas */
  }
}
```

**Output:** Bari screen par sidebar fixed rehta hai. Mobile par `static` hone se woh normal flow mein aa jata hai.

---

## 4. position: relative

### Definition
Element **Normal Flow mein hi rehta hai**, lekin `top`, `right`, `bottom`, `left` se apni **original position se** thora sa khisak sakta hai. Us ki **purani jagah khali (reserved) rehti hai**, is liye dusre elements apni jagah nahi badalte.

### Real-Life Analogy
Aap library mein apni **kursi thori peeche khiska** kar baith gaye. Lekin aap ki **purani jagah ab bhi aap ke naam** hai, dusra koi wahan nahi baith sakta, aur baaki sab ki kursiyan apni jagah par hain.

```
Pehle:                      Relative (left: 40px) ke baad:

[ A ] [ B ] [ C ]           [ A ] [ __ ] [ C ]
                                      [ B ]  <- B khisak gaya, lekin
                                              uski jagah khali reh gayi
```

### Syntax
```css
selector {
  position: relative;
  top: 10px;
  left: 20px;
}
```

### Do Bohat Zaroori Kaam
1. Element ko apni jagah se **thora hilana**.
2. Child par `position: absolute` lagani ho to parent ko **`relative`** bana dena (agle section mein tafseel).

---

### Example 1: Element ko Thora Hilana

```html
<div class="box">Box 1</div>
<div class="box shifted">Box 2 (hila hua)</div>
<div class="box">Box 3</div>
```

```css
.box {
  width: 150px;
  padding: 10px;
  margin-bottom: 10px;
  background-color: lightgreen;
}

.shifted {
  position: relative;
  left: 40px;
  top: 5px;
  background-color: orange;
}
```

**Output:** Box 2 apni jagah se 40px right aur 5px neeche khisak jayega. Box 1 aur Box 3 apni jagah par rahenge, aur Box 2 ki purani jagah khali rahegi.

---

### Example 2: Hover Par Upar Uthna (Card Effect)

```html
<div class="card">Hover karo mujh par</div>
```

```css
.card {
  position: relative;
  top: 0;
  width: 200px;
  padding: 20px;
  background-color: white;
  border: 2px solid purple;
  transition: top 0.3s;
}

.card:hover {
  top: -8px;     /* 8px upar uthega */
}
```

**Output:** Mouse laane par card halka sa upar uth jata hai. Yeh effect shopping websites ke product cards mein aam hai.

---

### Example 3: Parent Banana (Absolute Child ke liye)

```html
<div class="photo-box">
  <img src="student.jpg" alt="Student" width="200">
  <span class="tag">New</span>
</div>
```

```css
.photo-box {
  position: relative;   /* span ka reference point yeh banega */
  width: 200px;
}

.tag {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: red;
  color: white;
  padding: 3px 8px;
}
```

**Output:** "New" tag photo ke **top-right corner** mein aayega. `.photo-box` par `relative` na hota to tag poore page ke corner mein chala jata.

---

## 5. position: absolute

### Definition
Element ko **Normal Flow se nikal deta hai**, yaani us ki **jagah khatam** ho jati hai aur baaki elements us ki jagah le lete hain. Yeh apne **sab se qareeb positioned ancestor** (jis par `static` ke ilawa koi bhi position ho) ke mutabiq place hota hai. Agar aisa koi ancestor na ho to **poore page (`html`)** ke mutabiq place hota hai.

### Real-Life Analogy
Ek **photo frame** deewar par lagana hai. Aap kehte hain *"Frame ko **kamre ke left kone se 30cm** aur **chhat se 50cm neeche** lagao."* Frame ki position **kamre (parent)** ke hisab se naapi gayi. Agar frame ke aas paas ki jagah par pehle kuch rakha tha, to ab woh jagah khali nahi rehti, frame deewar par alag "tair" raha hai.

### Sab Se Zaroori Rule

```
absolute child  --->  dekhta hai: "Mera sab se qareeb positioned parent kaun hai?"

   Mil gaya     -->  Us parent ke mutabiq place hoga
   Nahi mila    -->  Poore page (html) ke mutabiq place hoga
```

> **Golden Rule:** Absolute element ka **parent hamesha `position: relative`** rakhein, taake child apne parent ke andar rahe.

### Syntax
```css
.parent {
  position: relative;
}

.child {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

### Absolute ke Natayej
- Element ki **jagah khatam** (parent ki height kam ho sakti hai).
- Width **content jitni** ho jati hai (jab tak width set na ho).
- Elements ek dusre ke **upar overlap** ho sakte hain.

---

### Example 1: Notification Badge

```html
<div class="bell">
  Notifications
  <span class="count">5</span>
</div>
```

```css
.bell {
  position: relative;
  display: inline-block;
  padding: 10px 20px;
  background-color: lightgray;
}

.count {
  position: absolute;
  top: -8px;
  right: -8px;
  background-color: red;
  color: white;
  border-radius: 50%;
  padding: 2px 7px;
  font-size: 12px;
}
```

**Output:** Red badge button ke top-right corner par thora bahar nikla hua nazar aayega, bilkul WhatsApp ya Facebook ke unread count ki tarah.

---

### Example 2: Image ke Upar Text (Overlay)

```html
<div class="banner">
  <img src="school.jpg" alt="School" width="400">
  <h2 class="banner-text">Welcome to Our School</h2>
</div>
```

```css
.banner {
  position: relative;
  width: 400px;
}

.banner img {
  display: block;
  width: 100%;
}

.banner-text {
  position: absolute;
  bottom: 20px;
  left: 20px;
  color: white;
  background-color: rgba(0, 0, 0, 0.5);
  padding: 8px 15px;
  margin: 0;
}
```

**Output:** Text image ke **neeche left kone** mein image ke upar likha hua aayega.

---

### Example 3: Bilkul Center Mein Rakhna (Popup / Modal)

```html
<div class="overlay">
  <div class="popup">
    <button class="close">X</button>
    <h3>Admission Open</h3>
    <p>Aaj hi apply karein.</p>
  </div>
</div>
```

```css
.overlay {
  position: relative;
  height: 300px;
  background-color: lightgray;
}

.popup {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);   /* khud ka aadha size wapas khench leta hai */
  width: 250px;
  padding: 20px;
  background-color: white;
  border: 2px solid navy;
}

.close {
  position: absolute;
  top: 5px;
  right: 5px;
}
```

**Output:** Popup parent ke **bilkul beech** mein aayega, aur close button popup ke top-right corner mein.

> **Center ka trick:** `top: 50%; left: 50%` se element ka **top-left corner** beech mein jata hai. `translate(-50%, -50%)` us ko apne **aadhe size jitna wapas** khench kar asal center mein le aata hai.

---

## 6. position: fixed

### Definition
Element **Normal Flow se nikal jata hai** aur **browser window (viewport)** ke mutabiq place hota hai. Page **scroll** karne par bhi yeh **apni jagah par hi rehta hai**.

### Real-Life Analogy
Class ke **board par laga hua clock**. Chahe teacher kahin bhi chali jaye, students kahin bhi baith jayein, clock **deewar par wahin laga rehta hai**.

### Absolute vs Fixed

| Feature | `absolute` | `fixed` |
|---------|------------|---------|
| Reference | Sab se qareeb positioned parent | **Browser window** |
| Scroll karne par | Page ke sath **scroll hota hai** | **Apni jagah par rehta hai** |

### Syntax
```css
selector {
  position: fixed;
  top: 0;
  right: 0;
}
```

---

### Example 1: Fixed Navigation Bar

```html
<nav class="navbar">Home | About | Contact</nav>
<div class="content">
  <p>Bohat lamba content yahan aayega...</p>
</div>
```

```css
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 15px;
  background-color: navy;
  color: white;
}

.content {
  margin-top: 60px;   /* navbar ke neeche chhup na jaye */
  height: 2000px;
}
```

**Output:** Scroll karne par navbar hamesha screen ke upar nazar aayega.

> **Tip:** Fixed element normal flow se nikal jata hai, is liye content ko `margin-top` ya `padding-top` dena zaroori hai, warna content navbar ke peeche chhup jata hai.

---

### Example 2: Floating WhatsApp / Chat Button

```html
<a href="#" class="chat-btn">Chat</a>
```

```css
.chat-btn {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background-color: green;
  color: white;
  padding: 15px 20px;
  border-radius: 50px;
  text-decoration: none;
}
```

**Output:** Chat button screen ke **neeche right corner** mein hamesha nazar aayega, chahe page kitna bhi scroll ho.

---

### Example 3: Cookie / Notice Banner

```html
<div class="cookie-bar">
  Hum cookies istemal karte hain.
  <button>Accept</button>
</div>
```

```css
.cookie-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 15px;
  background-color: #333;
  color: white;
  text-align: center;
}
```

**Output:** Screen ke neeche poori width wala banner hamesha dikhta rahega.

---

## 7. position: sticky

### Definition
Sticky element **pehle normal (relative ki tarah)** behave karta hai. Jab scroll karte karte woh **screen ke kisi kinare (jo `top`/`bottom` waghera mein diya ho) tak pahunchta hai** to wahan **chipak (stick) jata hai**, jab tak us ka parent screen par maujood ho.

### Real-Life Analogy
Aap **notebook mein sticky note** lagate hain. Jab tak aap page palat rahe hain, note apni jagah par hai. Lekin agar woh note **kitab ke kinare par laga ho** to kitab ke pages palatte waqt bhi wahin chipka rehta hai. Isi tarah table ka heading row scroll karte waqt upar chipak jata hai.

### Sticky ke Liye Shartein

1. **Kam az kam ek offset dena zaroori hai** (aam taur par `top: 0`).
2. Sticky element sirf apne **parent ke andar** hi chipakta hai. Parent khatam to sticky bhi khatam.
3. Kisi ancestor par `overflow: hidden`, `overflow: auto` ya `overflow: scroll` ho to sticky **kaam nahi karta**.

### Syntax
```css
selector {
  position: sticky;
  top: 0;
}
```

---

### Example 1: Sticky Header

```html
<header class="site-header">My School Website</header>
<main>
  <p>Bohat lamba content...</p>
</main>
```

```css
.site-header {
  position: sticky;
  top: 0;
  padding: 15px;
  background-color: navy;
  color: white;
}

main {
  height: 1500px;
}
```

**Output:** Header shuru mein apni normal jagah par hoga. Scroll karne par jab woh screen ke upar pahunchega to wahin chipak jayega. (Fixed ke muqable mein is mein content ke liye `margin-top` ki zaroorat nahi parti.)

---

### Example 2: Table ka Heading Row

```html
<div class="table-box">
  <table>
    <thead>
      <tr><th>Roll No</th><th>Name</th><th>Marks</th></tr>
    </thead>
    <tbody>
      <tr><td>1</td><td>Ayesha</td><td>95</td></tr>
      <tr><td>2</td><td>Fatima</td><td>90</td></tr>
      <tr><td>3</td><td>Zainab</td><td>88</td></tr>
    </tbody>
  </table>
</div>
```

```css
.table-box {
  height: 150px;
  overflow-y: auto;      /* is container ke andar scroll hoga */
}

th {
  position: sticky;
  top: 0;
  background-color: gold;
}
```

**Output:** Table ke andar scroll karne par heading row (Roll No, Name, Marks) upar chipki rahegi. Yahan scroll container `.table-box` hai, aur sticky usi ke mutabiq kaam karta hai.

---

### Example 3: Sticky Sidebar

```html
<div class="layout">
  <aside class="side">Menu</aside>
  <article class="article">Lamba article...</article>
</div>
```

```css
.layout {
  display: flex;
  gap: 20px;
  align-items: flex-start;   /* zaroori: warna sidebar poori height le leta hai */
}

.side {
  position: sticky;
  top: 20px;
  width: 150px;
  padding: 15px;
  background-color: lightblue;
}

.article {
  height: 1500px;
  flex: 1;
}
```

**Output:** Article scroll hota hai lekin sidebar screen se 20px neeche upar chipka rehta hai.

> **Aam ghalti:** Flex container mein `align-items: flex-start` na likhein to sidebar poori height le leta hai aur chipakne ke liye jagah hi nahi bachti.

---

## 8. z-index

### Definition
Jab elements **ek dusre ke upar overlap** karte hain to `z-index` decide karta hai ke **kaun upar** aur **kaun neeche** nazar aayega. Bara number = upar.

### Real-Life Analogy
Mez par **kai kitabein ek ke upar ek** rakhi hain. Jis kitab ka `z-index` zyada hai woh sab se upar, jis ka kam hai woh neeche dab jati hai.

```
z-index: 3   -->  [ Kitab C ]   (sab se upar)
z-index: 2   -->  [ Kitab B ]
z-index: 1   -->  [ Kitab A ]   (sab se neeche)
```

### Rules

1. `z-index` sirf **positioned elements** par kaam karta hai (`relative`, `absolute`, `fixed`, `sticky`). (Flex ya Grid ke children par bhi kaam karta hai.)
2. Bara number upar aata hai. Negative number bhi ho sakta hai (`-1`).
3. Agar `z-index` same ho to **jo HTML mein baad mein likha ho woh upar** aata hai.
4. Child apne **parent ke stacking group** se bahar nahi nikal sakta (stacking context).

### Syntax
```css
selector {
  position: relative;
  z-index: 10;
}
```

---

### Example 1: Overlapping Boxes

```html
<div class="stack">
  <div class="layer l1">1</div>
  <div class="layer l2">2</div>
  <div class="layer l3">3</div>
</div>
```

```css
.stack {
  position: relative;
  height: 150px;
}

.layer {
  position: absolute;
  width: 100px;
  height: 100px;
}

.l1 { background: tomato;     top: 0;    left: 0;    z-index: 3; }
.l2 { background: gold;       top: 30px; left: 30px; z-index: 2; }
.l3 { background: lightgreen; top: 60px; left: 60px; z-index: 1; }
```

**Output:** Box 1 (red) sab se upar, phir box 2 (yellow), aur box 3 (green) sab se neeche, chahe HTML mein woh aakhir mein likha ho.

---

### Example 2: Dropdown Menu Dusre Content ke Upar

```html
<div class="menu-box">
  <button>Menu</button>
  <ul class="dropdown">
    <li>Profile</li>
    <li>Settings</li>
  </ul>
</div>
<p class="below">Yeh paragraph menu ke neeche hai.</p>
```

```css
.menu-box {
  position: relative;
  display: inline-block;
}

.dropdown {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 100;           /* paragraph ke upar dikhne ke liye */
  background-color: white;
  border: 1px solid gray;
  list-style: none;
  margin: 0;
  padding: 5px 15px;
}
```

**Output:** Dropdown list paragraph ke **upar** khulti hai, usay dhakel nahi deti.

---

### Example 3: Fixed Navbar ko Sab Se Upar Rakhna

```html
<nav class="navbar">Navbar</nav>
<img src="banner.jpg" class="banner" alt="Banner">
```

```css
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  background-color: navy;
  color: white;
  z-index: 1000;      /* sab se upar */
}

.banner {
  position: relative;
  z-index: 1;
}
```

**Output:** Scroll karte waqt image navbar ke **neeche se guzarti** hai, upar nahi aati. Agar navbar par `z-index` na ho to positioned image us ke upar aa sakti hai.

---

## 9. Quick Comparison Table

| Feature | `static` | `relative` | `absolute` | `fixed` | `sticky` |
|---------|----------|------------|------------|---------|----------|
| Normal flow mein? | Haan | Haan | **Nahi** | **Nahi** | Haan |
| Purani jagah reserved? | Haan | Haan | Nahi | Nahi | Haan |
| `top/left` kaam karte hain? | Nahi | Haan | Haan | Haan | Haan |
| Reference | Koi nahi | Apni jagah | Positioned parent | Viewport | Scroll container |
| Scroll par | Scroll hota hai | Scroll hota hai | Scroll hota hai | **Jama rehta hai** | **Chipak jata hai** |
| `z-index` kaam karta hai? | Nahi | Haan | Haan | Haan | Haan |
| Aam istemal | Default | Thora hilana, parent banana | Badge, overlay, popup | Navbar, chat button | Sticky header |

### Yaad Rakhne Ka Aasan Tareeqa

- **static** = apni seat par
- **relative** = seat par rehkar thora khisko, jagah apni hai
- **absolute** = seat chhor di, parent ke mutabiq jagah lo
- **fixed** = screen par chipak jao, scroll se farq nahi
- **sticky** = normal rehte ho, kinare par pahunch kar chipak jao

### Konsi Position Kab Use Karein?

| Zaroorat | Position |
|----------|----------|
| Element ko thora sa hilana | `relative` |
| Badge ya icon kisi box ke corner mein | Parent `relative` + child `absolute` |
| Image ke upar text | Parent `relative` + text `absolute` |
| Popup ko center mein rakhna | `absolute` + `translate(-50%, -50%)` |
| Navbar jo hamesha upar rahe | `fixed` ya `sticky` |
| Floating chat button | `fixed` |
| Table heading scroll par chipki rahe | `sticky` |
| Elements ko overlap kar ke order dena | `z-index` |

---

## 10. Common Mistakes

| Ghalti | Wajah | Hal |
|--------|-------|-----|
| `top: 20px` kaam nahi kar raha | Position `static` hai (default) | `position: relative` ya koi aur value likhein |
| Absolute child poore page ke corner mein chala gaya | Parent par `position: relative` nahi | Parent par `position: relative` lagayein |
| Parent ki height zero ho gayi | Child `absolute` hone se flow se nikal gaya | Parent ko height dein |
| Fixed navbar ke peeche content chhup gaya | Fixed element ki jagah khatam ho jati hai | Content par `margin-top` ya `padding-top` dein |
| `sticky` kaam nahi kar raha | `top` nahi diya, ya parent par `overflow: hidden` hai | `top: 0` dein aur ancestors ka `overflow` check karein |
| `z-index` ka koi asar nahi | Element `static` hai | `position: relative` jaisi koi position dein |
| Bara `z-index` dene par bhi neeche hai | Parent ka stacking context alag hai | Parent ka `z-index` check karein |

---

## 11. Practice Tasks

1. Teen boxes banayen. Beech wale ko `position: relative` aur `left: 50px` dein. Dekhein ke baaki boxes hilte hain ya nahi.
2. Ek photo card banayen jis ke top-right corner mein "Sale" badge ho (relative parent aur absolute child).
3. Ek image par `position: absolute` se text neeche left mein likhein.
4. Ek popup box ko `top: 50%; left: 50%` aur `translate(-50%, -50%)` se bilkul center mein layen.
5. Ek `fixed` navigation bar banayen aur neeche lamba content rakh kar scroll karke dekhein.
6. Ek floating "Back to Top" button banayen jo screen ke neeche right corner mein rahe.
7. Ek table banayen jis ka heading row `sticky` ho.
8. Teen overlapping boxes banayen aur `z-index` se unka order badlein.

---

## 12. Mini Project Ideas

### Project 1: Product Card with Badge (Beginner)

**Requirements:**
- [ ] Card par image, naam aur qeemat
- [ ] Image ke top-left par "Sale" badge (`absolute`)
- [ ] Image ke top-right par heart icon (`absolute`)
- [ ] Hover par card thora upar uthe (`relative` + `top`)

### Project 2: School Landing Page (Intermediate)

**Requirements:**
- [ ] `fixed` ya `sticky` navbar
- [ ] Hero section mein image ke upar text (`absolute`)
- [ ] Neeche right corner mein floating "Contact" button (`fixed`)
- [ ] Cookie banner screen ke neeche (`fixed`)

### Project 3: Result Table Page (Intermediate)

**Requirements:**
- [ ] Students ki lambi table (kam az kam 15 rows)
- [ ] Heading row scroll par chipki rahe (`sticky`)
- [ ] Pehla column (naam) bhi chipka rahe (`sticky` + `left: 0`)

### Project 4: Popup / Modal Window (Advanced)

**Requirements:**
- [ ] "Open" button dabane par popup khule
- [ ] Peeche poori screen par dhundhla overlay (`fixed` + `inset: 0`)
- [ ] Popup bilkul center mein (`absolute` ya `fixed` + `translate`)
- [ ] Popup ke corner mein close button (`absolute`)
- [ ] Sahi `z-index` order (overlay, phir popup, phir close button)

---

## 13. Complete Practice Code

Neeche complete code hai. Isay `index.html` mein copy karke browser mein open karein aur scroll karke dekhein:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Position Practice</title>
  <style>
    * { box-sizing: border-box; }

    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 70px 20px 100px;   /* fixed navbar ke liye upar jagah */
      line-height: 1.6;
    }

    /* FIXED: navbar */
    .navbar {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 15px 20px;
      background-color: navy;
      color: white;
      z-index: 1000;
    }

    /* FIXED: floating button */
    .chat-btn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background-color: green;
      color: white;
      padding: 12px 20px;
      border-radius: 50px;
      text-decoration: none;
      z-index: 1000;
    }

    /* RELATIVE: thora hilana */
    .box {
      width: 150px;
      padding: 10px;
      margin-bottom: 10px;
      background-color: lightgreen;
    }
    .shifted {
      position: relative;
      left: 40px;
      background-color: orange;
    }

    /* RELATIVE parent + ABSOLUTE child: badge */
    .product {
      position: relative;
      width: 220px;
      padding: 20px;
      margin: 30px 0;
      border: 2px solid purple;
      text-align: center;
    }
    .badge {
      position: absolute;
      top: -10px;
      right: -10px;
      background-color: red;
      color: white;
      padding: 4px 10px;
      border-radius: 50px;
      font-size: 13px;
    }

    /* ABSOLUTE: center popup */
    .stage {
      position: relative;
      height: 200px;
      background-color: lightgray;
      margin-bottom: 30px;
    }
    .popup {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 200px;
      padding: 20px;
      background-color: white;
      border: 2px solid navy;
      text-align: center;
    }

    /* Z-INDEX: overlapping */
    .stack { position: relative; height: 170px; margin-bottom: 30px; }
    .layer { position: absolute; width: 100px; height: 100px; color: white; font-size: 24px; text-align: center; line-height: 100px; }
    .l1 { background: tomato;     top: 0;    left: 0;    z-index: 3; }
    .l2 { background: goldenrod;  top: 30px; left: 30px; z-index: 2; }
    .l3 { background: seagreen;   top: 60px; left: 60px; z-index: 1; }

    /* STICKY: scrolling area ke andar heading */
    .scroll-area {
      height: 180px;
      overflow-y: auto;
      border: 2px solid gray;
    }
    .sticky-head {
      position: sticky;
      top: 0;
      padding: 10px;
      background-color: gold;
      font-weight: bold;
    }
    .scroll-area p { padding: 0 10px; }
  </style>
</head>
<body>

  <nav class="navbar">Fixed Navbar | Home | About | Contact</nav>
  <a href="#" class="chat-btn">Chat</a>

  <h2>1. Relative</h2>
  <div class="box">Box 1</div>
  <div class="box shifted">Box 2 (hila hua)</div>
  <div class="box">Box 3</div>

  <h2>2. Relative parent + Absolute child</h2>
  <div class="product">
    <span class="badge">Sale</span>
    <h3>School Bag</h3>
    <p>Rs. 1500</p>
  </div>

  <h2>3. Absolute: Center Popup</h2>
  <div class="stage">
    <div class="popup">Main bilkul center mein hoon</div>
  </div>

  <h2>4. z-index</h2>
  <div class="stack">
    <div class="layer l1">1</div>
    <div class="layer l2">2</div>
    <div class="layer l3">3</div>
  </div>

  <h2>5. Sticky (neeche box ke andar scroll karein)</h2>
  <div class="scroll-area">
    <div class="sticky-head">Main chipka rahunga</div>
    <p>Line 1</p><p>Line 2</p><p>Line 3</p><p>Line 4</p><p>Line 5</p>
    <p>Line 6</p><p>Line 7</p><p>Line 8</p><p>Line 9</p><p>Line 10</p>
  </div>

  <p style="height: 600px;">Page scroll karke dekhein: navbar aur chat button apni jagah par rehte hain.</p>

</body>
</html>
```

---


