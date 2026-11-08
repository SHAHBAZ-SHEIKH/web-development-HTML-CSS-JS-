# JavaScript Class Notes

## 1. JavaScript kya hai?

JavaScript ek programming language hai jo website ko "zinda" (interactive) banati hai: button click par kuch hona, form check hona, menu khulna, ya live update dikhna.

**Real life example:** Website ko ek ghar samjhein.

| Technology | Ghar mein kya hai | Website mein kya kaam karti hai |
| --- | --- | --- |
| HTML | Ghar ka dhancha (deewarein, kamre) | Page ka structure aur content |
| CSS | Rang-o-roghan aur decoration | Design, colors, layout |
| JavaScript | Bijli, bell, darwaza khulna band hona | Behavior: click par action, logic, interaction |

Ghar ki deewarein HTML hain, rang CSS hai, lekin jab aap bell dabate hain aur awaaz aati hai, woh kaam JavaScript karti hai.

### JavaScript kyun use karte hain?

- **Interactivity:** Button click, slider, popup, dropdown menu.
- **Form validation:** Email ya password galat ho to foran message dikhana, server tak jaye baghair.
- **Dynamic content:** Page reload kiye baghair data badalna (jaise Facebook ka like count ya WhatsApp Web ke messages).
- **Web apps:** Gmail, Google Maps, Netflix jaisi applications.
- **Har jagah chalti hai:** Browser, server (Node.js), mobile apps aur games mein bhi.
- **Seekhna asaan:** Sirf browser aur ek text editor kafi hai, kisi khaas installation ki zaroorat nahi.

### Pehla JavaScript code

```javascript
console.log("Hello, JavaScript!");
```

**Class activity:** Browser mein `F12` dabayein, **Console** tab kholen, aur upar wali line likh kar `Enter` dabayein. Output foran nazar aa jayega.

---

## 2. alert() aur Function

### Function kya hota hai?

Function code ka ek chhota sa block hota hai jo ek khaas kaam karta hai. Jab bhi woh kaam chahiye, hum function ko **call** (bula) lete hain, har baar code dobara likhna nahi parta.

**Real life example:** Microwave ka "Start" button. Aap ko andar ki wiring ya process nahi pata, bas button dabate hain aur khana garam ho jata hai. Button dabana = function call, garam karna = function ka kaam.

### alert() kya hai?

`alert()` JavaScript ka ek **built-in function** hai jo browser mein ek popup message dikhata hai.

```javascript
alert("Assalam o Alaikum, Welcome to JavaScript!");
```

- `alert` = function ka naam
- `( )` = brackets, jin ke zariye function ko call karte hain
- `"..."` = **argument**, yaani woh message jo function ko diya ja raha hai
- `;` = statement ka end

**Note:** `alert()` chalne tak baqi code ruk jata hai, jab tak user "OK" na dabaye.

### Is tarah ke function ko kya kehte hain?

`alert()` ko **Built-in Function** (ya Predefined Function) kehte hain, kyun ke yeh JavaScript mein pehle se bana hua hai. Hamein isay khud likhna nahi parta, sirf use karna hota hai.

### Function ki types

| Type | Matlab | Example |
| --- | --- | --- |
| Built-in Function | JavaScript ne pehle se bana kar di hui | `alert()`, `prompt()`, `confirm()`, `console.log()` |
| User-defined Function | Jo programmer khud banata hai | `function salam() { ... }` |
| Function with Parameters | Jo input (value) le kar kaam karta hai | `function add(a, b) { ... }` |
| Function with Return Value | Jo kaam ke baad result wapas deta hai | `return a + b;` |
| Anonymous Function | Jis ka koi naam nahi hota | `function() { ... }` |
| Arrow Function | Chhota modern tareeqa | `(a, b) => a + b` |

(Class ke shuru mein pehli do types samjhana kafi hai, baqi aage ke lectures mein.)

### User-defined function ki misal

```javascript
function salam(naam) {
  alert("Assalam o Alaikum, " + naam);
}

salam("Ali");
salam("Sara");
```

Yahan `salam` humara apna function hai. Ek baar likha, aur alag alag naam ke sath do dafa call kiya.

### Dusre popup functions

| Function | Kaam | Example |
| --- | --- | --- |
| `alert()` | Sirf message dikhata hai | `alert("Hello")` |
| `confirm()` | OK / Cancel ka sawal puchta hai | `confirm("Kya aap sure hain?")` |
| `prompt()` | User se input leta hai | `prompt("Apna naam likhein")` |

---

## 3. Data Types

### Data type ka matlab kya hai?

Data type batata hai ke koi value **kis qism (kind)** ki hai: text hai, number hai, ya haan/naa wala jawab. JavaScript isi se samajhti hai ke us value ke sath kya kiya ja sakta hai.

**Real life example:** Aap ke paas alag alag cheezon ke liye alag dibbe hote hain: paani ke liye bottle, chawal ke liye dabba, paise ke liye wallet. Har cheez ki apni qism aur apna container hai. Isi tarah har value ki apni data type hoti hai.

### Primitive data types kya hote hain?

Primitive data types sab se basic aur simple types hain. Inme sirf **ek single value** hoti hai aur unhein baad mein change nahi kiya ja sakta (naya value dena parta hai).

| Data Type | Matlab | Example | Real life misal |
| --- | --- | --- | --- |
| String | Text (harf, lafz, jumla), quotes ke andar | `"Ali"`, `'Karachi'` | Aap ka naam, address |
| Number | Har qism ka number (poora ya decimal) | `25`, `99.5`, `-10` | Umar, price, marks |
| Boolean | Sirf do values: `true` ya `false` | `true`, `false` | Light on hai ya off? Fee jama hai ya nahi? |
| Undefined | Variable bana lekin value nahi di gayi | `undefined` | Khali dabba jis mein kuch rakha nahi |
| Null | Jaan boojh kar "kuch nahi" set kiya gaya | `null` | Dabba jis ko khud khali kiya |
| BigInt | Bohat bade numbers ke liye | `123456789012345678n` | Bohat bari raqam |
| Symbol | Har baar unique value (advanced) | `Symbol("id")` | Unique shanakhti number |

(Shuruat mein pehli teen types: **String, Number, Boolean** par focus karein.)

### 1. String

```javascript
let naam = "Ahmed";
let shehar = 'Lahore';
```

String hamesha **quotes** (`" "` ya `' '`) ke andar hoti hai. Agar number bhi quotes mein likha ho, woh string ban jata hai: `"25"` text hai, number nahi.

### 2. Number

```javascript
let umar = 20;
let price = 199.99;
```

Number par quotes nahi lagte. Isi par hum jama, minus, guna jaise hisaab kar sakte hain.

### 3. Boolean

```javascript
let loginHai = true;
let feeJamaHai = false;
```

Boolean sirf do jawab deta hai: **haan (true)** ya **naa (false)**. Yeh decisions lene (if/else) mein bohat kaam aata hai.

### typeof se type check karna

```javascript
console.log(typeof "Ali");   // string
console.log(typeof 25);      // number
console.log(typeof true);    // boolean
```

`typeof` ek operator hai jo bata deta hai ke value kis type ki hai.

---

## 4. Variables

### Variable kya hota hai?

Variable ek **naam wala dabba (container)** hai jis mein hum data store karte hain taake baad mein usay dobara use ya change kar sakein.

**Real life example:** Aap ke ghar mein ek dabba hai jis par likha hai "Cheeni". Is naam ki wajah se aap ko pata hai ke andar cheeni hai. Aap dabbe ka saman badal bhi sakte hain, magar naam wohi rehta hai. Variable bhi aisa hi hai: naam fix, value badal sakti hai.

### Variable kyun use karte hain?

- **Data yaad rakhne ke liye:** Naam, umar, price jaisi values store karna.
- **Dobara use karne ke liye:** Ek baar likhein, kayi jagah use karein.
- **Asaani se change karne ke liye:** Value ek jagah badlein, poore program mein update ho jaye.
- **Code ko samajhne layak banane ke liye:** `price` likhna `500` likhne se zyada wazeh hai.

### var se variable kaise banate hain?

`var` ek **keyword** hai jo JavaScript ko batata hai ke "main ek naya variable bana raha hoon".

```javascript
var naam = "Ali";
var umar = 20;
var paas = true;
```

**Syntax (tareeqa):**

```javascript
var variableName = value;
```

| Hissa | Matlab |
| --- | --- |
| `var` | Keyword: variable banane ka hukm |
| `naam` | Variable ka naam (aap khud chunte hain) |
| `=` | Assignment operator: value dene ke liye |
| `"Ali"` | Woh value jo store ho rahi hai |
| `;` | Statement khatam |

### Variable ki value use aur change karna

```javascript
var naam = "Ali";
alert(naam);        // Ali dikhayega

naam = "Sara";      // value badal di
alert(naam);        // ab Sara dikhayega
```

### Variable ke naam ke rules

- Naam **letter**, `_` ya `$` se shuru ho sakta hai, number se nahi.
- Space nahi ho sakti: `my name` galat hai, `myName` sahi hai.
- JavaScript **case-sensitive** hai: `naam` aur `Naam` do alag variables hain.
- Reserved words (jaise `var`, `if`, `function`) naam nahi ho sakte.
- Naam aisa rakhein jis se matlab samajh aaye, jaise `studentName`.

### Abhi `var` hi kyun?

`var` JavaScript ka sab se **pehla aur original** tareeqa hai variable banane ka, is liye seekhne ke liye bunyadi concept samajhna asaan hai. Aage chal kar modern JavaScript mein `let` aur `const` use hote hain, jin ka alag lecture hoga. Pehle `var` se concept pakka karna behtar hai.

---

## 5. Operators

### Operator ka matlab kya hai?

Operator ek **symbol** hota hai jo values par koi kaam (operation) karta hai, jaise jama, tarah tarah ka muqabla, ya value dena. Jin values par operator kaam karta hai unhein **operands** kehte hain.

```javascript
var total = 10 + 5;
// 10 aur 5 = operands
// +        = operator
```

**Real life example:** Calculator ke buttons (+, -, ×, ÷). Har button ek operator hai aur aap ke numbers operands.

### Operators kyun use karte hain?

- Hisaab kitaab (calculation) karne ke liye.
- Values ka muqabla karne ke liye (kaun bara, kaun barabar).
- Variables mein values store aur update karne ke liye.
- Faislay lene ke liye (agar ye aur wo dono sahi hon to...).

JavaScript mein 4 bunyadi operators sab se pehle seekhe jate hain:

### 1. Arithmetic Operators (hisaab ke operators)

Yeh numbers par math ke kaam karte hain.

| Operator | Naam | Example | Result |
| --- | --- | --- | --- |
| `+` | Jama (Addition) | `10 + 5` | `15` |
| `-` | Minus (Subtraction) | `10 - 5` | `5` |
| `*` | Guna (Multiplication) | `10 * 5` | `50` |
| `/` | Taqseem (Division) | `10 / 5` | `2` |
| `%` | Baqi (Modulus, remainder) | `10 % 3` | `1` |
| `**` | Power (Exponent) | `2 ** 3` | `8` |
| `++` | Ek se barhana (Increment) | `x++` | x mein 1 jama |
| `--` | Ek se ghatana (Decrement) | `x--` | x mein se 1 kam |

**Real life:** Dukan ka bill: `var bill = 500 + 250;`

```javascript
var a = 10;
var b = 3;
console.log(a + b);   // 13
console.log(a % b);   // 1  (10 ko 3 se taqseem karein to 1 bachta hai)
```

**Note:** `+` string ke sath **jorne (concatenation)** ka kaam bhi karta hai: `"Ali" + " Khan"` ka result `"Ali Khan"` hai.

### 2. Assignment Operators (value dene wale operators)

Yeh variable ko value dete hain. Sab se bunyadi `=` hai. Baqi shortcuts hain.

| Operator | Example | Matlab |
| --- | --- | --- |
| `=` | `x = 10` | x ko 10 de do |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `%=` | `x %= 5` | `x = x % 5` |

**Real life:** Wallet mein 1000 rupay hain, aur 200 aur mil gaye:

```javascript
var wallet = 1000;
wallet += 200;       // ab wallet = 1200
wallet -= 500;       // ab wallet = 700
```

**Dhyan dein:** `=` ka matlab "barabar hai" nahi, balke "value de do" hota hai.

### 3. Comparison Operators (muqabla karne wale operators)

Yeh do values ka muqabla karte hain aur hamesha **true ya false** (Boolean) result dete hain.

| Operator | Matlab | Example | Result |
| --- | --- | --- | --- |
| `==` | Value barabar hai? | `5 == "5"` | `true` |
| `===` | Value **aur type** dono barabar? | `5 === "5"` | `false` |
| `!=` | Barabar nahi? | `5 != 3` | `true` |
| `!==` | Value ya type barabar nahi? | `5 !== "5"` | `true` |
| `>` | Se bara | `10 > 5` | `true` |
| `<` | Se chhota | `10 < 5` | `false` |
| `>=` | Bara ya barabar | `10 >= 10` | `true` |
| `<=` | Chhota ya barabar | `5 <= 3` | `false` |

**Real life:** Exam mein pass hone ke liye marks 40 ya us se zyada chahiye:

```javascript
var marks = 55;
console.log(marks >= 40);   // true (pass)
```

**Best practice:** Hamesha `===` use karein, kyun ke yeh type bhi check karta hai aur ghalti ke chances kam hote hain.

### 4. Logical Operators (mantiqi operators)

Yeh kayi conditions ko mila kar ek final faisla (true/false) dete hain.

| Operator | Naam | Matlab | Example |
| --- | --- | --- | --- |
| `&&` | AND | **Dono** conditions sahi hon to true | `age >= 18 && hasCNIC` |
| `\|\|` | OR | **Koi ek** sahi ho to true | `isAdmin \|\| isOwner` |
| `!` | NOT | Natija ulta kar deta hai | `!isLoggedIn` |

**Real life:**

- **AND:** Gaari chalane ke liye aap ki umar 18 se zyada ho **aur** license bhi ho. Dono zaroori hain.
- **OR:** Aap bukhar hone **ya** thakan hone ki wajah se chhutti le sakte hain. Koi ek wajah kafi hai.
- **NOT:** Agar darwaza band **nahi** hai, to matlab khula hai.

```javascript
var umar = 20;
var licenseHai = true;

console.log(umar >= 18 && licenseHai);   // true
console.log(umar < 18 || licenseHai);    // true
console.log(!licenseHai);                // false
```

# JavaScript: Logical Operators (&&, ||, !)

> **Note:** Is lecture mein sirf Logical Operators ka concept hai. Humne `if / else` use nahi kiya, sirf `console.log()` se result dekha hai. Result hamesha **true** ya **false** hota hai.

---

## Lecture Roadmap

| Step | Topic | Maqsad |
| --- | --- | --- |
| 1 | Logical Operator kya hai? | Concept samajhna |
| 2 | AND (`&&`) | Sab conditions sahi hon |
| 3 | OR (`\|\|`) | Koi ek condition sahi ho |
| 4 | NOT (`!`) | Natija ulta karna |
| 5 | Teeno ka muqabla | Farq samajhna |
| 6 | Practice Questions | Khud karke seekhna |

---

## Step 1: Logical Operator kya hai?

### Pehle yaad karein: Boolean

Pichle lecture mein humne Boolean data type seekha tha. Boolean ki sirf do values hoti hain:

```javascript
true    // haan, sahi
false   // naa, ghalat
```

### Logical Operator ka matlab

Logical Operator **do ya zyada conditions ko jod kar** ek final jawab (**true ya false**) deta hai.

**Real life example:**

> Ek restaurant mein entry ke liye rule hai: *"Aap ke paas ticket ho **aur** aap ki age 12 saal se zyada ho."*

Yahan do conditions hain aur dono ko jod kar faisla hota hai. Programming mein yeh jorne ka kaam Logical Operators karte hain.

### JavaScript ke 3 Logical Operators

| Operator | Naam | Urdu mein | Kaam |
| --- | --- | --- | --- |
| `&&` | AND | **Aur** | **Sab** conditions true hon to true |
| `\|\|` | OR | **Ya** | **Koi ek** condition true ho to true |
| `!` | NOT | **Nahi / Ulta** | True ko false, false ko true bana deta hai |

### Logical Operators kyun use karte hain?

- Ek se zyada conditions ko **ek sath** check karne ke liye.
- Real life ke **mushkil faislay** (decisions) program mein likhne ke liye.
- Code chhota aur saaf rakhne ke liye (har condition alag likhne ki zaroorat nahi).

---

## Step 2: AND Operator (`&&`)

### Matlab

AND ka matlab hai **"aur"**. Result tab **true** hota hai jab **dono (ya saari) conditions true** hon. Agar **ek bhi false** ho to poora result **false**.

### Real life example

> Gaari chalane ka license tab milta hai jab aap ki age 18 se zyada ho **aur** aap ke paas CNIC ho.

Agar sirf age sahi hai aur CNIC nahi hai, to license nahi milega. **Dono zaroori hain.**

### Truth Table (AND)

| Condition 1 | Condition 2 | Condition 1 `&&` Condition 2 |
| --- | --- | --- |
| true | true | **true** |
| true | false | false |
| false | true | false |
| false | false | false |

**Yaad rakhne ka tareeqa:** AND sakht (strict) hai. **Result sirf ek surat mein true hai: dono true.**

### Diagram

```
┌─────────────┐
│ Condition 1 │── false ──►  Result: FALSE
└─────────────┘
   │
  true
   │
   ▼
┌─────────────┐
│ Condition 2 │── false ──►  Result: FALSE
└─────────────┘
   │
  true
   │
   ▼
 Result: TRUE   (dono true the)
```

**Diagram kaise parhein:** Box = condition check. Right side = jahan condition **false** nikli to seedha **FALSE**. Neeche = condition true nikli to agle box par jao. Jab saare boxes pass ho jayen, tab hi **TRUE** milta hai.

### Syntax

```javascript
condition1 && condition2
```

### Example 1: Driving License

```javascript
var age = 20;
var hasCNIC = true;

console.log(age >= 18 && hasCNIC);
```

**Output:**

```text
true
```

**Step by step:**

| Step | Condition | Result |
| --- | --- | --- |
| 1 | `age >= 18` yaani `20 >= 18` | true |
| 2 | `hasCNIC` | true |
| 3 | `true && true` | **true** |

### Example 2: Login (Username aur Password)

```javascript
var username = "ayesha";
var password = "1234";

console.log(username === "ayesha" && password === "1234");
```

**Output:** `true`

Agar password `"9999"` hota to output `false` aata, kyun ke dono sahi hone zaroori hain.

### Example 3: Scholarship

```javascript
var marks = 90;
var income = 60000;

console.log(marks >= 85 && income < 50000);
```

**Output:** `false`

| Step | Condition | Result |
| --- | --- | --- |
| 1 | `marks >= 85` yaani `90 >= 85` | true |
| 2 | `income < 50000` yaani `60000 < 50000` | **false** |
| 3 | `true && false` | **false** |

**Wajah:** Marks wali condition sahi hai, lekin income wali ghalat hai, is liye scholarship nahi milegi.

### Example 4: Exam Eligibility

```javascript
var attendance = 80;
var feePaid = true;

console.log(attendance >= 75 && feePaid);   // true
```

### Example 5: ATM Card

```javascript
var cardValid = true;
var pinCorrect = false;

console.log(cardValid && pinCorrect);   // false
```

### AND ke aur real life examples

| Situation | Condition 1 | Condition 2 |
| --- | --- | --- |
| Online class join karna | Internet chal raha ho | Laptop ki battery 20% se zyada ho |
| Passport apply karna | Age 18 se zyada ho | CNIC ho |
| Free delivery milna | Order 3000 se zyada ho | Customer member ho |
| Gym membership | Fee jama ho | Medical certificate ho |

---

## Step 3: OR Operator (`||`)

### Matlab

OR ka matlab hai **"ya"**. Result tab **true** hota hai jab **koi ek condition true** ho. Result sirf tab **false** hota hai jab **dono (ya saari) false** hon.

### Real life example

> Aap school se chhutti kar sakti hain agar aaj Sunday ho **ya** public holiday ho.

Dono mein se ek bhi wajah ho to chhutti mil jati hai. **Ek kafi hai.**

### Truth Table (OR)

| Condition 1 | Condition 2 | Condition 1 `\|\|` Condition 2 |
| --- | --- | --- |
| true | true | **true** |
| true | false | **true** |
| false | true | **true** |
| false | false | false |

**Yaad rakhne ka tareeqa:** OR naram (flexible) hai. **Result sirf ek surat mein false hai: dono false.**

### Diagram

```
┌─────────────┐
│ Condition 1 │── true ──►  Result: TRUE
└─────────────┘
   │
 false
   │
   ▼
┌─────────────┐
│ Condition 2 │── true ──►  Result: TRUE
└─────────────┘
   │
 false
   │
   ▼
 Result: FALSE   (dono false the)
```

**Diagram kaise parhein:** Jis box mein bhi condition **true** nikli, seedha right side par **TRUE** mil gaya, aage dekhne ki zaroorat nahi. Agar dono false hon to hi neeche **FALSE** milta hai.

### Syntax

```javascript
condition1 || condition2
```

**Tip:** `||` keyboard par Enter key ke upar wali `\` key ko **Shift** ke sath dabane se aata hai.

### Example 1: School Holiday

```javascript
var day = "Monday";
var isPublicHoliday = true;

console.log(day === "Sunday" || isPublicHoliday);
```

**Output:**

```text
true
```

**Step by step:**

| Step | Condition | Result |
| --- | --- | --- |
| 1 | `day === "Sunday"` yaani `"Monday" === "Sunday"` | false |
| 2 | `isPublicHoliday` | true |
| 3 | `false \|\| true` | **true** |

### Example 2: Payment

```javascript
var hasCash = false;
var hasCard = true;

console.log(hasCash || hasCard);   // true
```

### Example 3: Senior Citizen ya Student Discount

```javascript
var isStudent = false;
var age = 65;

console.log(isStudent || age >= 60);   // true
```

### Example 4: Medical Leave

```javascript
var hasFever = false;
var hasHeadache = false;

console.log(hasFever || hasHeadache);   // false
```

**Wajah:** Dono wajahein false hain, is liye chhutti ki koi wajah nahi.

### Example 5: Event Entry

```javascript
var hasTicket = true;
var hasInvitation = false;

console.log(hasTicket || hasInvitation);   // true
```

### OR ke aur real life examples

| Situation | Condition 1 | Condition 2 |
| --- | --- | --- |
| Result mein pass hona | Maths mein 40+ marks | English mein 40+ marks |
| Shopping payment | Cash ho | Card ho |
| Weekend trip | Din Saturday ho | Din Sunday ho |
| Cafeteria discount | Teacher ho | Discount coupon ho |

---

## Step 4: NOT Operator (`!`)

### Matlab

NOT ka matlab hai **"nahi"** ya **"ulta"**. Yeh sirf **ek** value par kaam karta hai aur usay **ulta** kar deta hai.

- `true` ko `false` bana deta hai.
- `false` ko `true` bana deta hai.

### Real life example

> Agar darwaza band **nahi** hai (NOT closed), to iska matlab darwaza khula hai.

### Truth Table (NOT)

| Value | `!` Value |
| --- | --- |
| true | **false** |
| false | **true** |

### Syntax

```javascript
!condition
```

### Example 1: Door Lock

```javascript
var isDoorLocked = true;

console.log(!isDoorLocked);   // false
```

### Example 2: Phone Silent Mode

```javascript
var isSilent = false;

console.log(!isSilent);   // true (phone silent nahi hai, yaani awaaz aayegi)
```

### Example 3: NOT ke sath comparison (brackets zaroori hain)

```javascript
var age = 16;

console.log(!(age >= 18));   // true
```

**Step by step:**

| Step | Kaam | Result |
| --- | --- | --- |
| 1 | `age >= 18` yaani `16 >= 18` | false |
| 2 | `!false` | **true** |

**Dhyan dein:** Comparison ke sath NOT lagana ho to condition ko **brackets `( )`** mein likhein.

---

## Step 5: Teeno Operators ka Muqabla

| | AND (`&&`) | OR (`\|\|`) | NOT (`!`) |
| --- | --- | --- | --- |
| Urdu mein | **Aur** | **Ya** | **Ulta** |
| Kitni values par kaam? | Do ya zyada | Do ya zyada | Sirf ek |
| Kab true? | Jab **sab** true hon | Jab **koi ek** true ho | Jab value **false** ho |
| Kab false? | Jab **koi ek** false ho | Jab **sab** false hon | Jab value **true** ho |
| Mizaj | Sakht (strict) | Naram (flexible) | Ulta karne wala |
| Real life | License: age **aur** CNIC | Payment: cash **ya** card | Darwaza band **nahi** hai |

### Ek hi situation, teeno operators ke sath

```javascript
var hasTicket = true;
var hasInvitation = false;

console.log(hasTicket && hasInvitation);   // false (dono chahiye the)
console.log(hasTicket || hasInvitation);   // true  (ek kafi hai)
console.log(!hasTicket);                   // false (true ka ulta)
```

### Common Mistakes (aam ghaltiyan)

| Ghalat | Sahi | Wajah |
| --- | --- | --- |
| `age >= 18 && <= 60` | `age >= 18 && age <= 60` | Dono taraf **poori condition** likhni hoti hai |
| `day = "Sunday" \|\| isHoliday` | `day === "Sunday" \|\| isHoliday` | `=` value assign karta hai, muqabla nahi, `===` use karein |
| `&` ya `\|` (ek ek) | `&&` ya `\|\|` (do do) | Logical operators mein **do symbols** hote hain |
| `!age >= 18` | `!(age >= 18)` | Comparison ke sath NOT lagate waqt **brackets** zaroori hain |

---

## Step 6: Practice Questions (Students ke liye)

**Hidayat:** Har question mein `console.log()` se expression ka result print karna hai. Result `true` ya `false` aayega.

### Section A: AND (`&&`) Questions

**Question 1: Library Membership**

- **Scenario:** Library mein membership tab milti hai jab student ki age 15 se zyada ho **aur** uske paas student card ho. Hira ki age 17 saal hai aur uske paas student card hai.
- **Given:** `var age = 17;` aur `var hasStudentCard = true;`
- **Task:** AND operator se dono conditions check karein aur result console mein print karein.
- **Expected Output:** `true`

**Question 2: Online Class**

- **Scenario:** Online class join karne ke liye internet chal raha ho **aur** laptop ki battery 20% se zyada ho. Sana ka internet chal raha hai lekin battery sirf 15% hai.
- **Given:** `var internetOn = true;` aur `var battery = 15;`
- **Task:** AND operator se result print karein.
- **Expected Output:** `false`

**Question 3: Free Delivery**

- **Scenario:** Online store par free delivery tab milti hai jab order 3000 rupay ya us se zyada ka ho **aur** customer store ka member ho. Maryam ka order 3500 rupay ka hai lekin woh member nahi hai.
- **Given:** `var orderAmount = 3500;` aur `var isMember = false;`
- **Task:** AND operator se result print karein.
- **Expected Output:** `false`

**Question 4: Passport Application**

- **Scenario:** Passport apply karne ke liye age 18 saal ya us se zyada ho **aur** CNIC ho. Fatima ki age 25 saal hai aur uske paas CNIC hai.
- **Given:** `var age = 25;` aur `var hasCNIC = true;`
- **Task:** AND operator se result print karein.
- **Expected Output:** `true`

### Section B: OR (`||`) Questions

**Question 5: Cafeteria Discount**

- **Scenario:** Cafeteria mein discount unhein milta hai jo teacher hon **ya** jinke paas discount coupon ho. Zainab teacher nahi hai lekin uske paas coupon hai.
- **Given:** `var isTeacher = false;` aur `var hasCoupon = true;`
- **Task:** OR operator se result print karein.
- **Expected Output:** `true`

**Question 6: Weekend Trip**

- **Scenario:** Ayesha ki family trip tab hoti hai jab din Saturday ho **ya** Sunday ho. Aaj Sunday hai.
- **Given:** `var day = "Sunday";`
- **Task:** OR operator se `day === "Saturday"` aur `day === "Sunday"` ko jor kar result print karein.
- **Expected Output:** `true`

**Question 7: Concert Entry**

- **Scenario:** Concert mein entry ke liye ticket ho **ya** invitation card ho. Noor ke paas na ticket hai na invitation card.
- **Given:** `var hasTicket = false;` aur `var hasInvitation = false;`
- **Task:** OR operator se result print karein.
- **Expected Output:** `false`

**Question 8: Subject Pass**

- **Scenario:** Ek competition mein shamil hone ke liye Maths mein 40 marks ya English mein 40 marks hone chahiye (koi ek kafi hai). Areeba ke Maths mein 35 aur English mein 55 marks hain.
- **Given:** `var mathMarks = 35;` aur `var englishMarks = 55;`
- **Task:** OR operator se `mathMarks >= 40` aur `englishMarks >= 40` ko jor kar result print karein.
- **Expected Output:** `true`

### Section C: NOT (`!`) Questions

**Question 9: Rain Check**

- **Scenario:** Aaj baarish nahi ho rahi. Humein check karna hai ke "baarish nahi ho rahi" wali baat sahi hai ya nahi.
- **Given:** `var isRaining = false;`
- **Task:** NOT operator se `isRaining` ko ulta karke result print karein.
- **Expected Output:** `true`

**Question 10: WiFi Status**

- **Scenario:** Ek app ko check karna hai ke WiFi connected **nahi** hai kya. Abhi WiFi connected hai.
- **Given:** `var isWifiConnected = true;`
- **Task:** NOT operator se result print karein.
- **Expected Output:** `false`

**Question 11: Underage Check**

- **Scenario:** Hania ki age 16 saal hai. Humein check karna hai ke woh adult **nahi** hai kya (adult ka matlab age 18 ya zyada).
- **Given:** `var age = 16;`
- **Task:** NOT aur comparison operator ko brackets ke sath use karke `!(age >= 18)` ka result print karein.
- **Expected Output:** `true`

### Section D: Predict the Output (Bina run kiye batayein)

**Question 12:**

```javascript
var a = true;
var b = false;

console.log(a && b);
console.log(a || b);
console.log(!a);
console.log(!b);
```

- **Task:** Chaaron lines ka output likhein.
- **Expected Output:**

```text
false
true
false
true
```

**Question 13:**

```javascript
var x = 10;

console.log(x > 5 && x < 8);
console.log(x > 5 || x < 8);
console.log(!(x > 5));
```

- **Task:** Teenon lines ka output likhein aur har step ki wajah batayein.
- **Expected Output:**

```text
false
true
false
```

**Wajah:** `x > 5` true hai aur `x < 8` false hai. AND mein ek false ho to result false, OR mein ek true ho to result true, aur `!(true)` false hota hai.

### Section E: Truth Table Challenge

**Question 14:** Neeche di gayi table khud complete karein.

| A | B | A `&&` B | A `\|\|` B | `!A` |
| --- | --- | --- | --- | --- |
| true | true | ? | ? | ? |
| true | false | ? | ? | ? |
| false | true | ? | ? | ? |
| false | false | ? | ? | ? |

---

## Final Revision

| Concept | Yaad rakhein |
| --- | --- |
| Logical Operator | Conditions ko jor kar true ya false deta hai |
| `&&` (AND) | **Sab** true hon to true |
| `\|\|` (OR) | **Koi ek** true ho to true |
| `!` (NOT) | Value ko **ulta** kar deta hai |
| AND sirf true kab? | Jab dono true hon |
| OR sirf false kab? | Jab dono false hon |
| Comparison ke sath NOT | Brackets `( )` zaroor lagayein |
| Condition likhna | Dono taraf **poori condition** likhein |

---

## Teacher Solutions (Answer Key)

### Section A: AND

```javascript
// Question 1
var age = 17;
var hasStudentCard = true;
console.log(age > 15 && hasStudentCard);        // true

// Question 2
var internetOn = true;
var battery = 15;
console.log(internetOn && battery > 20);        // false

// Question 3
var orderAmount = 3500;
var isMember = false;
console.log(orderAmount >= 3000 && isMember);   // false

// Question 4
var age = 25;
var hasCNIC = true;
console.log(age >= 18 && hasCNIC);              // true
```

### Section B: OR

```javascript
// Question 5
var isTeacher = false;
var hasCoupon = true;
console.log(isTeacher || hasCoupon);                      // true

// Question 6
var day = "Sunday";
console.log(day === "Saturday" || day === "Sunday");      // true

// Question 7
var hasTicket = false;
var hasInvitation = false;
console.log(hasTicket || hasInvitation);                  // false

// Question 8
var mathMarks = 35;
var englishMarks = 55;
console.log(mathMarks >= 40 || englishMarks >= 40);       // true
```

### Section C: NOT

```javascript
// Question 9
var isRaining = false;
console.log(!isRaining);        // true

// Question 10
var isWifiConnected = true;
console.log(!isWifiConnected);  // false

// Question 11
var age = 16;
console.log(!(age >= 18));      // true
```

### Section D: Predict the Output

- **Question 12:** `false`, `true`, `false`, `true`
- **Question 13:** `false`, `true`, `false`

### Section E: Truth Table Answer

| A | B | A `&&` B | A `\|\|` B | `!A` |
| --- | --- | --- | --- | --- |
| true | true | **true** | **true** | **false** |
| true | false | **false** | **true** | **false** |
| false | true | **false** | **true** | **true** |
| false | false | **false** | **false** | **true** |

### Khulasa (Summary)

| Operator Type | Kaam | Result kya aata hai |
| --- | --- | --- |
| Arithmetic | Hisaab kitaab | Number |
| Assignment | Variable ko value dena | Variable update hota hai |
| Comparison | Do values ka muqabla | true / false |
| Logical | Conditions ko jorna | true / false |

### Class Practice Questions

1. Apna naam aur umar variables mein store karein aur `alert()` se dikhayein.
2. Do numbers ka jama, minus, guna aur taqseem console mein print karein.
3. `var salary = 30000;` banayein aur `+=` se 5000 ka bonus jama karein.
4. `5 == "5"` aur `5 === "5"` ka result alag kyun aata hai? Samjhayein.
5. Aisi condition likhein jo check kare ke koi shakhs 18 se bara **aur** 60 se chhota hai.
