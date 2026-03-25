# Day 23 — External CSS, Classes, IDs & Specificity

📖 **Type:** Theory Session
🕐 **Duration:** 2 Hours
📚 **Unit:** 4 — CSS

---

## Learning Objectives

By the end of this session, students will be able to:
- Create and link external CSS files
- Use classes and IDs effectively
- Understand CSS specificity and cascading rules
- Use advanced selectors (child, sibling, pseudo-class, pseudo-element)

---

## 1. External CSS Workflow

### File Structure

```
project/
├── index.html
├── about.html
├── contact.html
└── css/
    └── style.css
```

### Linking CSS

```html
<!-- index.html -->
<head>
    <link rel="stylesheet" href="css/style.css">
</head>
```

> **Benefit:** Change `style.css` once → every page updates automatically. Perfect for multi-page websites.

---

## 2. Advanced Selectors

### Combinator Selectors

| Selector | Example | Selects |
|----------|---------|---------|
| Descendant | `div p` | `<p>` anywhere inside `<div>` |
| Child | `div > p` | `<p>` direct child of `<div>` |
| Adjacent sibling | `h2 + p` | First `<p>` right after `<h2>` |
| General sibling | `h2 ~ p` | All `<p>` after `<h2>` (same parent) |

```css
/* Only paragraphs DIRECTLY inside article */
article > p { color: #333; }

/* First paragraph after any heading */
h2 + p { font-size: 1.1em; font-weight: 600; }
```

### Attribute Selectors

```css
/* Input with type="email" */
input[type="email"] { border: 2px solid #1565C0; }

/* Links that open in new tab */
a[target="_blank"] { color: #E91E63; }

/* Links starting with https */
a[href^="https"] { color: green; }

/* Links ending with .pdf */
a[href$=".pdf"]::after { content: " 📄"; }
```

### Pseudo-Class Selectors

```css
/* Mouse hover */
a:hover { color: #E91E63; text-decoration: underline; }

/* Currently focused input */
input:focus { border-color: #1565C0; outline: none; box-shadow: 0 0 5px rgba(21,101,192,0.3); }

/* First and last child */
li:first-child { font-weight: bold; }
li:last-child { border-bottom: none; }

/* Every odd row (zebra striping) */
tr:nth-child(odd) { background: #f5f5f5; }
tr:nth-child(even) { background: white; }

/* Empty elements */
p:empty { display: none; }
```

### Pseudo-Element Selectors

```css
/* First letter of paragraph */
p::first-letter {
    font-size: 2em;
    color: #1565C0;
    float: left;
    margin-right: 5px;
}

/* First line of paragraph */
p::first-line { font-weight: bold; }

/* Add content before/after */
.required::after {
    content: " *";
    color: red;
}

.external-link::after {
    content: " ↗";
}
```

---

## 3. CSS Specificity

> **Analogy:** Specificity is like a **priority system**. Imagine a chain of command in the military — a General's order (ID) overrides a Colonel's (class), which overrides a Soldier's (element).

### Specificity Calculation

| Selector Type | Weight | Example |
|-------------- |--------|---------|
| Inline style | 1000 | `style="color:red"` |
| ID | 100 | `#header` |
| Class, attribute, pseudo-class | 10 | `.highlight`, `:hover` |
| Element, pseudo-element | 1 | `p`, `::first-line` |

### Examples

```css
p { color: blue; }                    /* Specificity: 0-0-1 = 1 */
.text { color: green; }              /* Specificity: 0-1-0 = 10 */
#intro { color: red; }               /* Specificity: 1-0-0 = 100 */
p.text { color: orange; }            /* Specificity: 0-1-1 = 11 */
#intro p.text { color: purple; }     /* Specificity: 1-1-1 = 111 */
```

### The Cascade Order

When multiple rules conflict, the browser resolves using:
1. **Importance** — `!important` wins (but avoid using it)
2. **Specificity** — Higher specificity wins
3. **Source Order** — Last rule wins (if specificity is equal)

```css
p { color: blue; }
p { color: red; }     /* Red wins — same specificity, later in file */

.text { color: green; }
p { color: red; }       /* Green wins — class (10) > element (1) */
```

---

## 4. Organizing CSS

### Good Practices

```css
/* =========================
   1. Reset / Base Styles
   ========================= */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', sans-serif;
    font-size: 16px;
    line-height: 1.6;
    color: #333;
}

/* =========================
   2. Layout
   ========================= */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* =========================
   3. Components
   ========================= */
.card {
    background: white;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.btn {
    display: inline-block;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}
.btn-primary { background: #1565C0; color: white; }
.btn-success { background: #4CAF50; color: white; }

/* =========================
   4. Utility Classes
   ========================= */
.text-center { text-align: center; }
.mt-20 { margin-top: 20px; }
.mb-20 { margin-bottom: 20px; }
```

---

## Practice Exercise

1. Create a multi-page mini website (3 pages) sharing one external CSS file:
   - `index.html` — Home page
   - `about.html` — About page
   - `contact.html` — Contact page
   - `css/style.css` — Shared stylesheet

2. Use at least 5 different selector types: element, class, ID, pseudo-class, attribute.

3. Create a specificity challenge: write conflicting rules and predict which color wins.

---

## Summary

| Concept | Key Takeaway |
|---------|-------------|
| External CSS | One `.css` file, many HTML pages |
| Child selector | `div > p` — direct children only |
| Pseudo-class | `:hover`, `:nth-child()`, `:focus` |
| Pseudo-element | `::first-letter`, `::before`, `::after` |
| Specificity | ID (100) > Class (10) > Element (1) |
| Cascade | Last rule wins if specificity is equal |

---

*Day 23 of 55 | Unit 4 — CSS | Web Technology (25BCA060)*
