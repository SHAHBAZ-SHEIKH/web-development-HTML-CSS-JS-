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