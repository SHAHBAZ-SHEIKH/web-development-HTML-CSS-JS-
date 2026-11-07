# CSS Box Model & Essential Properties Guide

**Topics covered:** Box Model, Display (block / inline / inline-block / none), Text Decoration, List Style, Font, Background Image

Yeh guide students ke liye hai. Har topic ko definition, syntax, real-life analogy aur **3 practical examples** ke sath explain kiya gaya hai.

---

## Table of Contents

1. [Box Model](#1-box-model)
2. [Display Property](#2-display-property)
3. [Text Decoration](#3-text-decoration)
4. [List Style](#4-list-style)
5. [Font Properties](#5-font-properties)
6. [Background Image](#6-background-image)
7. [Quick Cheat Sheet](#7-quick-cheat-sheet)
8. [Practice Tasks](#8-practice-tasks)
9. [Mini Project Ideas](#9-mini-project-ideas)
10. [Complete Practice Code](#10-complete-practice-code)

---

## 1. Box Model

### Definition
CSS mein **har HTML element ek rectangular box** hota hai. **Box Model** us box ki structure ko describe karta hai. Yeh 4 layers par mushtamil hota hai:

| Layer | Meaning |
|-------|---------|
| **Content** | Asal text ya image jo box ke andar hai |
| **Padding** | Content aur border ke darmiyan **andar ki jagah** |
| **Border** | Padding ke ird-gird **line / frame** |
| **Margin** | Border ke bahar, dusre elements se **faasla** |

### Real-Life Analogy
Ek **gift box** socho:
- **Content** = andar rakha hua gift
- **Padding** = gift aur box ki deewar ke darmiyan bhara hua bubble wrap
- **Border** = gift box ki deewar
- **Margin** = shelf par is box aur dusre boxes ke darmiyan khali jagah

### Visual Representation

```
+--------------------------------------------+
|                 MARGIN                     |
|   +------------------------------------+   |
|   |             BORDER                 |   |
|   |   +----------------------------+   |   |
|   |   |         PADDING            |   |   |
|   |   |   +--------------------+   |   |   |
|   |   |   |      CONTENT       |   |   |   |
|   |   |   +--------------------+   |   |   |
|   |   +----------------------------+   |   |
|   +------------------------------------+   |
+--------------------------------------------+
```

### Syntax
```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  margin: 30px;
}
```

### Total Size Kaise Calculate Hota Hai?

Default (`content-box`) mein:

```
Total Width  = width + (padding left + right) + (border left + right) + (margin left + right)
Total Height = height + (padding top + bottom) + (border top + bottom) + (margin top + bottom)
```

**Example:** `width: 200px; padding: 20px; border: 5px; margin: 30px;`

```
Visible box width = 200 + (20+20) + (5+5)  = 250px
Total space used  = 250 + (30+30)          = 310px
```

### Padding / Margin Shorthand

```css
margin: 10px;                 /* chaaron taraf 10px */
margin: 10px 20px;            /* top-bottom 10px | left-right 20px */
margin: 10px 20px 30px;       /* top 10px | left-right 20px | bottom 30px */
margin: 10px 20px 30px 40px;  /* top | right | bottom | left (clockwise) */
```

> **Yaad rakhne ka tareeqa:** Clockwise (ghari ki tarah) = **Top, Right, Bottom, Left** (TRouBLe).

### `box-sizing` Property

| Value | Behavior |
|-------|----------|
| `content-box` (default) | `width` sirf content ki hoti hai, padding aur border upar se add hote hain |
| `border-box` | `width` mein padding aur border **shamil** hote hain (layout aasan hota hai) |

```css
* {
  box-sizing: border-box;   /* Professional developers yeh hamesha use karte hain */
}
```

---

### Example 1: Student ID Card

```html
<div class="id-card">
  <h3>Ayesha Khan</h3>
  <p>Class: 9th | Roll No: 21</p>
</div>
```

```css
.id-card {
  width: 250px;
  padding: 15px;
  border: 3px solid darkgreen;
  margin: 20px;
  background-color: lightgreen;
}
```

**Output:** Card ke content aur border ke darmiyan 15px ki jagah hai (padding), aur card ke bahar 20px ka faasla hai (margin).

---

### Example 2: Notice Board Card

```html
<div class="notice">Kal school band rahega.</div>
<div class="notice">Exam schedule jald aayega.</div>
```

```css
.notice {
  width: 300px;
  padding: 10px 20px;
  border: 2px dashed red;
  margin-bottom: 25px;
}
```

**Output:** Dono notices ke darmiyan 25px ka vertical gap aayega (margin-bottom).

---

### Example 3: Button Design

```html
<button class="btn">Submit</button>
```

```css
.btn {
  padding: 12px 30px;
  border: none;
  border-radius: 8px;
  background-color: purple;
  color: white;
  margin: 10px;
}
```

**Output:** Padding ki wajah se button bara aur comfortable nazar aayega, `border-radius` se corners round honge.

---

## 2. Display Property

### Definition
`display` property decide karti hai ke element page par **kaise behave kare**: nayi line se shuru ho, ya line mein rahe, ya bilkul chhup jaye.

### Real-Life Analogy
- **block** = Class mein har student apni **alag line (row)** mein baithi hai
- **inline** = Students ek hi **bench par ek dusre ke sath** baithi hain
- **inline-block** = Ek hi line mein baithi hain, lekin har ek apni **desk ka size** rakh sakti hai
- **none** = Student **absent** hai, class mein jagah bhi nahi leti

### Quick Comparison

| Property | New line se shuru? | width/height set kar sakte hain? | Space leta hai? |
|----------|--------------------|-----------------------------------|------------------|
| `block` | Haan | Haan | Haan (poori width) |
| `inline` | Nahi | **Nahi** | Sirf content jitna |
| `inline-block` | Nahi | Haan | Content / set size jitna |
| `none` | N/A | N/A | **Nahi (hide)** |

> **Default values:** `div`, `p`, `h1-h6`, `ul`, `li` = **block** | `span`, `a`, `strong`, `em`, `img` = **inline**

---

### 2.1 `display: block`

**Definition:** Element hamesha **nayi line** se shuru hota hai aur available **poori width** leta hai. Width, height, margin, padding sab properly kaam karte hain.

**Syntax:**
```css
selector {
  display: block;
}
```

#### Example 1: Span ko Block Banana

```html
<span class="name">Ayesha</span>
<span class="name">Fatima</span>
<span class="name">Zainab</span>
```

```css
.name {
  display: block;
  background-color: lightblue;
  margin-bottom: 5px;
}
```

**Output:** Teeno names alag alag lines mein aayenge, aur har ek ka background poori width tak failega.

#### Example 2: Link ko Full-Width Button Banana

```html
<a href="#" class="full-btn">Login</a>
```

```css
.full-btn {
  display: block;
  padding: 12px;
  background-color: green;
  color: white;
  text-align: center;
  text-decoration: none;
}
```

**Output:** Link poori width wale button ki tarah nazar aayega.

#### Example 3: Image ke neeche Gap Khatam Karna

```html
<img src="photo.jpg" class="photo" alt="Student">
```

```css
.photo {
  display: block;
  width: 200px;
  margin: 0 auto;   /* center mein */
}
```

**Output:** Image `block` hone ki wajah se `margin: 0 auto` se **center** ho jayegi (inline element par yeh kaam nahi karta).

---

### 2.2 `display: inline`

**Definition:** Element **usi line mein** rehta hai jahan pichla content khatam hua. Sirf apne content jitni jagah leta hai. **Width aur height kaam nahi karti**, aur top/bottom margin bhi effective nahi hota.

**Syntax:**
```css
selector {
  display: inline;
}
```

#### Example 1: Div ko Inline Banana

```html
<div class="tag">HTML</div>
<div class="tag">CSS</div>
<div class="tag">JavaScript</div>
```

```css
.tag {
  display: inline;
  background-color: yellow;
  padding: 5px;
}
```

**Output:** Teeno tags ek hi line mein aayenge.

#### Example 2: Sentence ke andar Highlight

```html
<p>Aaj ka topic <span class="highlight">Box Model</span> hai.</p>
```

```css
.highlight {
  background-color: orange;
  font-weight: bold;
}
```

**Output:** Sirf "Box Model" highlight hoga, aur sentence line mein rahega.

#### Example 3: Inline Navigation Links

```html
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Contact</a>
```

```css
a {
  display: inline;
  margin-right: 15px;
}
```

**Output:** Teeno links ek hi line mein, 15px ke gap ke sath.

---

### 2.3 `display: inline-block`

**Definition:** Inline ki tarah **same line** mein rehta hai, lekin block ki tarah **width, height, margin, padding** bhi accept karta hai. Cards aur buttons ki row banane ke liye best hai.

**Syntax:**
```css
selector {
  display: inline-block;
}
```

#### Example 1: Cards ki Row

```html
<div class="card">Card 1</div>
<div class="card">Card 2</div>
<div class="card">Card 3</div>
```

```css
.card {
  display: inline-block;
  width: 120px;
  height: 80px;
  background-color: lightpink;
  margin: 10px;
  text-align: center;
}
```

**Output:** Teeno cards ek hi row mein, har ek ka fixed size.

#### Example 2: Horizontal Menu

```html
<ul class="menu">
  <li>Home</li>
  <li>About</li>
  <li>Contact</li>
</ul>
```

```css
.menu li {
  display: inline-block;
  padding: 10px 20px;
  background-color: navy;
  color: white;
  margin-right: 5px;
}
```

**Output:** List items horizontal menu ban jayenge, padding bhi apply hogi.

#### Example 3: Badges

```html
<span class="badge">New</span>
<span class="badge">Sale</span>
```

```css
.badge {
  display: inline-block;
  width: 60px;
  height: 25px;
  line-height: 25px;
  text-align: center;
  background-color: crimson;
  color: white;
  border-radius: 5px;
}
```

**Output:** Chhote fixed-size badges ek hi line mein.

---

### 2.4 `display: none`

**Definition:** Element ko page se **mukammal tor par hide** kar deta hai. Element ki **jagah bhi khatam** ho jati hai, goya woh HTML mein hai hi nahi.

**Syntax:**
```css
selector {
  display: none;
}
```

#### Example 1: Hidden Message

```html
<p class="secret">Yeh message nazar nahi aayega.</p>
<p>Yeh message nazar aayega.</p>
```

```css
.secret {
  display: none;
}
```

**Output:** Sirf doosra paragraph show hoga.

#### Example 2: Mobile par Element Hide Karna

```html
<div class="ad-banner">Advertisement</div>
```

```css
@media (max-width: 600px) {
  .ad-banner {
    display: none;
  }
}
```

**Output:** Choti screen (mobile) par ad banner hide ho jayega.

#### Example 3: Dropdown Menu

```html
<div class="dropdown">
  <button>Menu</button>
  <ul class="dropdown-list">
    <li>Profile</li>
    <li>Settings</li>
  </ul>
</div>
```

```css
.dropdown-list {
  display: none;
}

.dropdown:hover .dropdown-list {
  display: block;
}
```

**Output:** List pehle hidden hoti hai. Button par mouse le jane se list show ho jati hai.

---

### `display: none` vs `visibility: hidden`

| Property | Element hide? | Jagah leta hai? |
|----------|---------------|------------------|
| `display: none` | Haan | **Nahi** (jagah khatam) |
| `visibility: hidden` | Haan | **Haan** (khali jagah rehti hai) |

---

## 3. Text Decoration

### Definition
`text-decoration` property text par **line (underline, overline, line-through)** lagane ya hataane ke liye use hoti hai.

### Real-Life Analogy
Copy mein jab aap koi important word par **underline** lagate hain, ya galat answer par **line cross** karte hain, to yeh bilkul wahi kaam hai.

### Values

| Value | Effect |
|-------|--------|
| `none` | Koi line nahi (links se underline hatane ke liye) |
| `underline` | Text ke **neeche** line |
| `overline` | Text ke **upar** line |
| `line-through` | Text ke **beech mein** se line (strike) |

### Syntax
```css
selector {
  text-decoration: underline;
}

/* Full syntax: line | style | color | thickness */
selector {
  text-decoration: underline wavy red 2px;
}
```

### Additional Properties

| Property | Values |
|----------|--------|
| `text-decoration-line` | underline, overline, line-through |
| `text-decoration-style` | solid, double, dotted, dashed, wavy |
| `text-decoration-color` | Koi bhi color |
| `text-decoration-thickness` | 1px, 3px waghera |
| `text-underline-offset` | Underline aur text ke darmiyan gap |

---

### Example 1: Link se Underline Hatana

```html
<a href="#" class="clean-link">Click Here</a>
```

```css
.clean-link {
  text-decoration: none;
  color: blue;
}

.clean-link:hover {
  text-decoration: underline;
}
```

**Output:** Link normal halat mein underline ke baghair hoga, mouse laane par underline aa jayegi.

---

### Example 2: Old Price (Discount Shop)

```html
<p>
  <span class="old-price">Rs. 2000</span>
  <span class="new-price">Rs. 1500</span>
</p>
```

```css
.old-price {
  text-decoration: line-through;
  color: gray;
}

.new-price {
  color: green;
  font-weight: bold;
}
```

**Output:** Purani qeemat par line lag jayegi aur nayi qeemat green bold mein nazar aayegi.

---

### Example 3: Fancy Heading Underline

```html
<h2 class="fancy">Welcome to Class</h2>
```

```css
.fancy {
  text-decoration: underline wavy purple;
  text-decoration-thickness: 3px;
  text-underline-offset: 6px;
}
```

**Output:** Heading ke neeche purple wavy (lehrati hui) moti underline aayegi.

---

## 4. List Style

### Definition
`list-style` property `<ul>` (unordered) aur `<ol>` (ordered) lists ke **markers (bullets / numbers)** ko control karti hai.

### Real-Life Analogy
Shopping list mein kabhi **bullets (•)** lagate hain, kabhi **numbers (1, 2, 3)**, aur kabhi kuch bhi nahi. `list-style` yehi decide karti hai.

### Properties

| Property | Kaam |
|----------|------|
| `list-style-type` | Marker ki type (disc, circle, square, decimal, none...) |
| `list-style-position` | Marker list item ke **andar** (`inside`) ya **bahar** (`outside`) |
| `list-style-image` | Marker ki jagah **custom image** |
| `list-style` | Teeno ka **shorthand** |

### Common `list-style-type` Values

| Value | Result |
|-------|--------|
| `disc` | Bhara hua dot (ul ka default) |
| `circle` | Khali circle |
| `square` | Square |
| `decimal` | 1, 2, 3 (ol ka default) |
| `lower-alpha` | a, b, c |
| `upper-roman` | I, II, III |
| `none` | Koi marker nahi |

### Syntax
```css
ul {
  list-style-type: square;
}

/* Shorthand: type | position | image */
ul {
  list-style: square inside;
}
```

---

### Example 1: Different Bullet Types

```html
<ul class="subjects">
  <li>Math</li>
  <li>Science</li>
  <li>English</li>
</ul>
```

```css
.subjects {
  list-style-type: square;
  color: darkblue;
}
```

**Output:** Teeno subjects ke samne square bullets aayenge.

---

### Example 2: Numbered List with Roman Numbers

```html
<ol class="rules">
  <li>Time par aao</li>
  <li>Homework karo</li>
  <li>Bari ka ehtram karo</li>
</ol>
```

```css
.rules {
  list-style-type: upper-roman;
}
```

**Output:** I, II, III ke numbers aayenge.

---

### Example 3: Navigation Menu ke liye Bullets Khatam Karna

```html
<ul class="nav">
  <li><a href="#">Home</a></li>
  <li><a href="#">About</a></li>
  <li><a href="#">Contact</a></li>
</ul>
```

```css
.nav {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav li {
  display: inline-block;
  margin-right: 15px;
}
```

**Output:** Bullets khatam, items ek hi line mein. Har professional website ke menu mein yehi technique use hoti hai.

> **Tip:** `list-style: none;` ke sath hamesha `padding: 0; margin: 0;` bhi likhein, kyunke browser lists par default padding deta hai.

---

## 5. Font Properties

### Definition
Font properties text ki **shakal (style)** control karti hain: kaisa font, kitna bara, kitna mota, waghera.

### Real-Life Analogy
Aap copy mein kabhi **moti handwriting** mein heading likhte hain, kabhi **patli aur chhoti** mein notes. Font properties yehi control karti hain.

### Main Properties

| Property | Kaam | Example Values |
|----------|------|----------------|
| `font-family` | Font ka naam | `Arial`, `"Times New Roman"`, `sans-serif` |
| `font-size` | Text ka size | `16px`, `1.2em`, `1rem` |
| `font-weight` | Text ki motai (boldness) | `normal`, `bold`, `100` se `900` |
| `font-style` | Text ka style | `normal`, `italic`, `oblique` |
| `font-variant` | Small caps | `small-caps` |
| `line-height` | Lines ke darmiyan gap | `1.5`, `24px` |
| `letter-spacing` | Letters ke darmiyan gap | `2px` |
| `font` | **Shorthand** | `italic bold 18px/1.5 Arial` |

### Font Family: Fallback System

```css
body {
  font-family: "Poppins", Arial, sans-serif;
}
```

Browser pehle `Poppins` try karega. Agar na mile to `Arial`, aur woh bhi na mile to koi bhi `sans-serif` font.

### Generic Font Families

| Family | Description |
|--------|-------------|
| `serif` | Haashiye (tails) wale fonts, jaise Times New Roman |
| `sans-serif` | Saaf, seedhe fonts, jaise Arial |
| `monospace` | Har letter ki barabar width, code ke liye |
| `cursive` | Handwriting style |

### Units Ka Farq

| Unit | Matlab |
|------|--------|
| `px` | Fixed pixel size |
| `em` | Parent ke font-size ke mutabiq |
| `rem` | Root (`html`) ke font-size ke mutabiq |
| `%` | Parent ka percentage |

### Google Fonts Use Karna

```html
<head>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
</head>
```

```css
body {
  font-family: "Poppins", sans-serif;
}
```

---

### Example 1: Heading aur Paragraph

```html
<h1 class="title">My School</h1>
<p class="text">Yahan hum CSS seekh rahe hain.</p>
```

```css
.title {
  font-family: Georgia, serif;
  font-size: 40px;
  font-weight: bold;
  color: darkred;
}

.text {
  font-family: Arial, sans-serif;
  font-size: 18px;
  line-height: 1.6;
}
```

**Output:** Heading bara aur serif font mein, paragraph saaf sans-serif font mein aur lines ke darmiyan achhi spacing.

---

### Example 2: Quote Design

```html
<blockquote class="quote">
  Ilm hasil karna har insaan ka haq hai.
</blockquote>
```

```css
.quote {
  font-family: "Times New Roman", serif;
  font-style: italic;
  font-size: 22px;
  letter-spacing: 1px;
  color: gray;
}
```

**Output:** Quote italic style mein, halki letter-spacing ke sath.

---

### Example 3: Shorthand Property

```html
<p class="note">Important Note</p>
```

```css
.note {
  /* style | weight | size/line-height | family */
  font: italic bold 20px/1.5 Verdana, sans-serif;
}
```

**Output:** Ek hi line mein style, weight, size, line-height aur family set ho gayi.

> **Zaroori:** Shorthand mein `font-size` aur `font-family` **lazmi** hote hain, warna property kaam nahi karti.

---

## 6. Background Image

### Definition
`background-image` property kisi element ke peeche **image lagane** ke liye use hoti hai.

### Real-Life Analogy
Aap kamre ki deewar par **wallpaper** lagate hain. Furniture (content) us ke aage rakhi hoti hai. Background image bhi element ka wallpaper hai.

### Properties

| Property | Kaam | Values |
|----------|------|--------|
| `background-image` | Image set karna | `url("image.jpg")` |
| `background-repeat` | Image repeat ho ya nahi | `repeat`, `no-repeat`, `repeat-x`, `repeat-y` |
| `background-size` | Image ka size | `cover`, `contain`, `100px 200px`, `100%` |
| `background-position` | Image ki jagah | `center`, `top right`, `50% 50%` |
| `background-attachment` | Scroll behavior | `scroll`, `fixed` |
| `background` | **Shorthand** | Sab ek sath |

### Important Values

| Value | Matlab |
|-------|--------|
| `cover` | Image poora box **cover** kare (image crop ho sakti hai) |
| `contain` | Poori image **nazar aaye** (khali jagah reh sakti hai) |
| `no-repeat` | Image sirf ek baar |
| `fixed` | Scroll karne par image **jaam** rahe (parallax effect) |

### Syntax
```css
selector {
  background-image: url("images/school.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

/* Shorthand */
selector {
  background: url("images/school.jpg") no-repeat center / cover;
}
```

---

### Example 1: Hero Section

```html
<div class="hero">
  <h1>Welcome to Our School</h1>
</div>
```

```css
.hero {
  height: 400px;
  background-image: url("school.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: white;
  text-align: center;
  padding-top: 150px;
}
```

**Output:** Poore section ke peeche school ki image aayegi, aur uske upar white heading.

---

### Example 2: Pattern Background (Repeat)

```html
<div class="pattern">Pattern Background</div>
```

```css
.pattern {
  height: 200px;
  background-image: url("small-flower.png");
  background-repeat: repeat;
}
```

**Output:** Chhoti image baar baar repeat hokar poora background bhar degi.

---

### Example 3: Fixed Background (Parallax Effect)

```html
<div class="parallax">
  <h2>Scroll karke dekhein</h2>
</div>
```

```css
.parallax {
  height: 500px;
  background-image: url("mountain.jpg");
  background-attachment: fixed;
  background-size: cover;
  background-position: center;
}
```

**Output:** Page scroll karne par text hilta hai lekin background image apni jagah par rehti hai.

---

### Bonus: Dark Overlay (Text Readable Banane ke liye)

```css
.hero {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("school.jpg");
  background-size: cover;
}
```

**Output:** Image ke upar halki kaali layer aa jati hai, jis se white text saaf parha jata hai.

---

## 7. Quick Cheat Sheet

| Topic | Property | Common Value |
|-------|----------|--------------|
| Box Model | `padding` | `20px` |
| Box Model | `border` | `2px solid black` |
| Box Model | `margin` | `0 auto` (center) |
| Box Model | `box-sizing` | `border-box` |
| Display | `display` | `block`, `inline`, `inline-block`, `none` |
| Text | `text-decoration` | `none`, `underline`, `line-through` |
| List | `list-style` | `none`, `square`, `decimal` |
| Font | `font-family` | `Arial, sans-serif` |
| Font | `font-size` | `16px` |
| Font | `font-weight` | `bold`, `700` |
| Background | `background-image` | `url("img.jpg")` |
| Background | `background-size` | `cover` |

---

## 8. Practice Tasks

1. Ek **Student Card** banayen jis mein width, padding, border aur margin chaaron use hon.
2. Teen `span` elements ko `display: block` karke dekhein, phir `inline-block` karke difference note karein.
3. Ek link banayen jis se underline hat jaye aur hover par wapas aa jaye.
4. Ek `ul` ke bullets khatam karke usay horizontal navigation menu banayen.
5. Google Fonts se koi font laga kar heading aur paragraph ka design banayen.
6. Ek section par background image lagayen, `cover` aur `center` ke sath, aur uske upar text likhein.

---

## 9. Mini Project Ideas

Yeh teeno projects upar ke **saare topics** (Box Model, Display, Text Decoration, List Style, Font, Background Image) ek sath practice karwate hain.

### Project 1: Student Profile Card (Beginner)

**Requirements:**
- [ ] Card par width, padding, border, margin (Box Model)
- [ ] Card ke peeche background image ya color
- [ ] Naam, class aur subjects ke liye alag fonts aur sizes
- [ ] Subjects ki list (custom bullets ke sath)
- [ ] "Contact Me" link bina underline ke, hover par underline

### Project 2: School Website Navigation Bar (Beginner to Intermediate)

**Requirements:**
- [ ] `ul` list se bullets khatam karke horizontal menu
- [ ] Menu items `inline-block` mein padding ke sath
- [ ] Links se underline khatam
- [ ] Hover par background change
- [ ] Dropdown menu (`display: none` aur hover par `block`)
- [ ] Neeche hero section jis mein background image aur text overlay ho

### Project 3: Product / Shop Card Page (Intermediate)

**Requirements:**
- [ ] 3 se 4 product cards ek row mein (`inline-block`)
- [ ] Har card mein image, naam, purani qeemat (`line-through`) aur nayi qeemat
- [ ] Card par border, padding, margin, aur `border-radius`
- [ ] "Out of Stock" tag (`display: none` se hide / show practice)
- [ ] Page ke liye Google Font aur background pattern

### Project 4: Personal Portfolio Page (Advanced)

**Requirements:**
- [ ] Hero section (fixed background image / parallax)
- [ ] About Me, Skills (list-style), Projects (cards) sections
- [ ] Consistent fonts, colors aur spacing
- [ ] Mobile par kuch elements hide karna (`@media` aur `display: none`)

---

## 10. Complete Practice Code

Neeche complete code hai. Isay `index.html` mein copy karke browser mein open karein:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Box Model & Properties Practice</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; }

    body {
      font-family: "Poppins", Arial, sans-serif;
      font-size: 16px;
      line-height: 1.6;
      margin: 0;
      padding: 20px;
      background-color: #f4f4f4;
    }

    /* Navigation: list-style, display, text-decoration */
    .nav { list-style: none; padding: 0; margin: 0 0 20px; background: navy; }
    .nav li { display: inline-block; }
    .nav a {
      display: block;
      padding: 12px 20px;
      color: white;
      text-decoration: none;
    }
    .nav a:hover { background: royalblue; text-decoration: underline; }

    /* Box Model: profile card */
    .card {
      width: 300px;
      padding: 20px;
      border: 3px solid darkgreen;
      margin: 20px 0;
      background-color: lightgreen;
      border-radius: 10px;
    }
    .card h3 { margin-top: 0; font-weight: 700; }

    /* Text decoration: price */
    .old-price { text-decoration: line-through; color: gray; }
    .new-price { color: green; font-weight: bold; }

    /* Display: inline-block boxes */
    .box {
      display: inline-block;
      width: 100px;
      height: 70px;
      background: lightpink;
      margin: 5px;
      text-align: center;
      line-height: 70px;
    }

    /* Display: none */
    .hidden { display: none; }

    /* Background image: hero */
    .hero {
      height: 250px;
      background-image:
        linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
        url("https://images.unsplash.com/photo-1503676260728-1c00da094a0b?w=1200");
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      color: white;
      text-align: center;
      padding-top: 90px;
      border-radius: 10px;
    }
  </style>
</head>
<body>

  <ul class="nav">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>

  <div class="hero">
    <h1>Welcome to Our School</h1>
  </div>

  <div class="card">
    <h3>Ayesha Khan</h3>
    <p>Class: 9th | Roll No: 21</p>
    <ul>
      <li>Math</li>
      <li>Science</li>
      <li>English</li>
    </ul>
  </div>

  <p>
    <span class="old-price">Rs. 2000</span>
    <span class="new-price">Rs. 1500</span>
  </p>

  <div class="box">Box 1</div>
  <div class="box">Box 2</div>
  <div class="box">Box 3</div>

  <p class="hidden">Yeh text nazar nahi aayega.</p>

</body>
</html>
```

---

**Happy Learning!** Agar koi sawal ho to class mein pooch lein.
