# First Web Development Class — 2 Hour Plan

A simple, story-driven plan for teaching your very first web development class. The goal: get students excited, not overwhelmed, and make sure they understand *why* things work the way they do.

---

## Overview (2 hours = 120 minutes)

| Time | Topic |
|---|---|
| 15 min | Ice-breaker + Internet vs Web |
| 20 min | The History of HTML (Tim Berners-Lee) |
| 15 min | The Real Purpose of HTML |
| 30 min | Live Coding — Basic HTML Tags |
| 10 min | Break |
| 20 min | CSS Introduction |
| 10 min | Mini Activity + Wrap-up |

---

## Part 1: Ice-breaker — Internet vs Web

Start by asking: **"How many websites have you already used today?"** WhatsApp Web, Google, YouTube, an online food order app — it's all web technology.

Then clear up a common confusion: **Internet** and **World Wide Web** are not the same thing.

- **Internet** = a giant network connecting computers worldwide (like a network of roads)
- **Web (WWW)** = what travels on those roads — websites and pages you access through the internet

**Example:** "The Internet is like all the roads and highways in a country connecting every city. The Web is the cars and buses that travel on those roads, taking you from one place to another. Without the Internet, the Web has nowhere to travel."

---

## Part 2: The History of HTML — Why It Was Invented

This part matters a lot — once students know *why* something was created, the *how* becomes much easier to understand.

In **1989–90 at CERN (Switzerland)**, a scientist named **Tim Berners-Lee** worked at a research lab where scientists from all over the world shared their research.

**The problem:** Every scientist stored their data differently — different computers, different software, different formats. Reading someone else's work was a nightmare.

**Example:** "Imagine every student in a class wrote their assignment in a different language — some in Urdu, some in English, some in Chinese — and the teacher had to read and grade all of them. That's the exact problem Tim Berners-Lee had with his colleagues' research papers."

**His solution:** Create a **simple, common language** that *any* computer, anywhere in the world, could understand — Windows, Mac, anything. He built three things:

1. **HTML** — a standard way to write documents (what the content *is*)
2. **HTTP** — a protocol (a method) to send those documents from one computer to another
3. **URL** — a unique address for every document

**Example:** "Imagine sending a letter to someone. You need three things: (1) a language/format everyone understands to write the letter (HTML), (2) a postal service to carry it (HTTP), (3) the correct home address to deliver it to (URL). Tim Berners-Lee invented all three."

**The first website launched in 1991** — just plain text, no design, no colors. Very basic.

**Important point to mention in class:** Tim Berners-Lee **never patented HTML** — he kept it free for the whole world. That's a big reason the web grew so huge. If he had charged money for it, the internet might not be what it is today.

---

## Part 3: What HTML Is Actually For

Now for the core concept — HTML has **one real purpose**:

> **To give content structure — so the browser knows what is a heading, what is a paragraph, what is an image, what is a link.**

HTML was **not built for design**. It was built purely to give content **meaning and structure**. (Design came later, with CSS.)

**Example (this one lands really well):** "Imagine you're writing a book. You need to know which part is the **title**, which is a **chapter heading**, which is a **normal paragraph**, and where an **image** goes. Labeling all of this is exactly what HTML does — like sticky notes that say 'this is a heading' or 'this is important' — except in a language computers understand."

**Second useful example:** "HTML is the structure of a house — the walls, the roof, the doors, the rooms. Without it, a house can't stand. But structure alone doesn't make a house beautiful — it needs paint (CSS) and electricity/functionality (JavaScript). But where would you even put the paint and wiring if there's no structure first?"

This is exactly why HTML is always taught first — it's the foundation.

---

## Part 4: What "Markup Language" Actually Means

Students often get confused by the name itself: **HyperText Markup Language**. Break it down:

- **HyperText** = text that **links** to other text/pages (like the blue clickable links on Wikipedia that take you to another page)
- **Markup** = labeling content using **tags** to say what each piece of content is

**Example:** "Imagine a teacher checking your notebook and marking it up with a red pen — 'this is a heading', 'this is a spelling mistake', 'this is important'. HTML tags are exactly like those red-pen markings — they tell the browser what role each piece of content plays."

Write on the board:
```html
<h1>This Is a Heading</h1>
<p>This is a normal paragraph.</p>
```

Explain: "`<h1>` is a tag telling the browser: 'Show this text bigger and bold, because it's a heading.' It's just like the teacher's red-pen note."

---

## Part 5: Live Coding — Now Students Are Ready

After the history and purpose, students *want* to code because they understand why they're learning it. Now move to hands-on practice.

**Step 1:** Open VS Code or an online editor (CodePen / Replit both work fine).

**Step 2:** Type this out together, live:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My First Website</title>
</head>
<body>
  <h1>Hello, World!</h1>
  <p>This is my first website.</p>
</body>
</html>
```

**Explain each tag using everyday comparisons:**
- `<h1>` = the biggest heading (like a newspaper headline)
- `<p>` = a paragraph (normal text)
- `<img>` = adds an image
- `<a>` = a link (like the link in an Instagram bio)
- `<ul>` / `<li>` = a list (like a grocery list)

**Activity (very important):** Have every student add their own name, a short paragraph about themselves, and an image. This builds real confidence — "I can actually do this."

---

## Break (10 minutes)

Let them relax. When you come back, ask a quick recap question from the first half to re-engage everyone.

---

## Part 6: CSS Introduction

Explain: CSS = Cascading Style Sheets. Its job is to make HTML **look good**.

**Example:** "HTML is your body, CSS is your clothes and styling. Without CSS, a website is plain and boring — just like a person with no clothes on, structurally fine, but not exactly presentable."

Do a live demo:
```html
<h1 style="color: blue; text-align: center;">Hello, World!</h1>
```

Change the color, change the font size — students see instant visual results, which is very exciting for beginners.

---

## Part 7: Mini Project + Wrap-up

Ask everyone to build a small **"About Me"** page: their name, a photo, 2–3 lines about themselves, and one link. If time allows, let a few students show their work to the class.

**Wrap-up talking points:**
- "Today we learned how websites are built — HTML gives structure, CSS gives design."
- "Next class, we'll learn JavaScript, which makes a website 'come alive' — like something happening when you click a button."
- Homework: finish the "About Me" page and bring it to the next class.

---

## Extra Tips for a Great Class

- **Code right after every new concept.** Just listening is boring — showing results immediately keeps attention.
- **Normalize errors.** Say: "Getting errors while coding is completely normal — that's literally how you learn."
- **Reuse the analogies.** The restaurant, the house, the clothes — repeating them helps things stick.
- If there's extra time, open a popular website (like Google's homepage) and use **Inspect Element** to show its raw HTML. Students love seeing "I could build something like this."
