# Day 14 — HTML5 Basics & Semantic Elements

📖 **Type:** Theory Session
🕐 **Duration:** 2 Hours
📚 **Unit:** 3 — HTML5

---

## Learning Objectives

By the end of this session, students will be able to:
- Explain the advantages of HTML5 over HTML4
- Use semantic elements for page structure
- Differentiate between semantic and non-semantic elements
- Build a well-structured page using HTML5 semantic tags

---

## 1. What is HTML5?

HTML5 is the **fifth and current version** of HTML, finalized in 2014 as a "Living Standard" (continuously updated). It introduces new elements, APIs, and capabilities.

### HTML5 vs HTML4

| Feature | HTML4 | HTML5 |
|---------|-------|-------|
| Doctype | Complex: `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"...>` | Simple: `<!DOCTYPE html>` |
| Multimedia | Needs Flash/plugins | Native `<audio>` & `<video>` |
| Graphics | Not built-in | `<canvas>` & `<svg>` |
| Structure | `<div id="header">` | `<header>`, `<nav>`, `<main>` |
| Forms | Basic inputs | Date, email, range, color pickers |
| Storage | Cookies only | localStorage, sessionStorage |
| Offline | Not supported | Service Workers, App Cache |

---

## 2. Semantic Elements

### What is Semantic HTML?

> **Analogy:** Imagine reading a newspaper. You can tell the **headline**, **article**, **sidebar**, and **advertisement** apart just by looking — because they each have a distinct visual layout with clear meaning. **Semantic HTML** gives web page sections the same kind of built-in meaning.

**Semantic elements** clearly describe their meaning to both the browser and the developer.

| Non-Semantic (meaningless) | Semantic (meaningful) |
|---------------------------|----------------------|
| `<div id="header">` | `<header>` |
| `<div id="nav">` | `<nav>` |
| `<div class="article">` | `<article>` |
| `<div id="footer">` | `<footer>` |

### HTML5 Semantic Elements

```
┌─────────────────────────────────────────────┐
│  <header>                                   │
│    Logo, site title, search bar             │
├─────────────────────────────────────────────┤
│  <nav>                                      │
│    Home | About | Courses | Contact         │
├────────────────────────────┬────────────────┤
│  <main>                    │  <aside>       │
│  ┌──────────────────────┐  │  Sidebar       │
│  │ <article>            │  │  - Links       │
│  │   <h2>Title</h2>     │  │  - Ads         │
│  │   <p>Content...</p>  │  │  - Related     │
│  │   <section>          │  │                │
│  │     Sub-section      │  │                │
│  │   </section>         │  │                │
│  │ </article>           │  │                │
│  └──────────────────────┘  │                │
├────────────────────────────┴────────────────┤
│  <footer>                                   │
│    Copyright, contact, social links         │
└─────────────────────────────────────────────┘
```

### Tag Reference

| Tag | Purpose | Analogy |
|-----|---------|---------|
| `<header>` | Page or section header | Letterhead on stationery |
| `<nav>` | Navigation links | Table of contents |
| `<main>` | Primary page content (only one per page) | The main article |
| `<article>` | Self-contained content (blog post, news story) | A newspaper article |
| `<section>` | Thematic grouping of content | A chapter in a book |
| `<aside>` | Side content (ads, related links) | Sidebar in a newspaper |
| `<footer>` | Page or section footer | Fine print at the bottom |
| `<figure>` | Image/diagram with caption | Photo with caption |
| `<figcaption>` | Caption for `<figure>` | The caption text |
| `<details>` | Expandable/collapsible content | FAQ accordion |
| `<summary>` | Heading for `<details>` | FAQ question |
| `<mark>` | Highlighted text | Highlighter pen |
| `<time>` | Date/time markup | Calendar entry |

---

## 3. Building a Page with Semantic HTML5

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BCA Department - Mandsaur University</title>
</head>
<body>

    <header>
        <h1>Mandsaur University</h1>
        <p>Department of Computer Applications (BCA)</p>
    </header>

    <nav>
        <a href="#about">About</a> |
        <a href="#courses">Courses</a> |
        <a href="#faculty">Faculty</a> |
        <a href="#contact">Contact</a>
    </nav>

    <main>
        <article>
            <h2 id="about">About the Department</h2>
            <p>The BCA department was established in <time datetime="2015">2015</time> 
               with a vision to produce skilled IT professionals.</p>
            
            <section>
                <h3>Our Vision</h3>
                <p>To be a center of excellence in computer education.</p>
            </section>
            
            <section>
                <h3>Our Mission</h3>
                <p>To provide quality education through theoretical and practical learning.</p>
            </section>
        </article>

        <article id="courses">
            <h2>Courses</h2>
            
            <details>
                <summary><strong>Semester I</strong></summary>
                <ul>
                    <li>Programming in C</li>
                    <li>Computer Fundamentals</li>
                    <li>Mathematics I</li>
                </ul>
            </details>

            <details open>
                <summary><strong>Semester II (Current)</strong></summary>
                <ul>
                    <li>Web Technology</li>
                    <li>Data Structures</li>
                    <li>Discrete Mathematics</li>
                </ul>
            </details>
        </article>

        <article id="faculty">
            <h2>Faculty</h2>
            <figure>
                <img src="https://via.placeholder.com/200x200?text=HOD" alt="HOD Photo" width="200">
                <figcaption><strong>Dr. Faculty Name</strong> — Head of Department</figcaption>
            </figure>
        </article>
    </main>

    <aside>
        <h3>Quick Links</h3>
        <ul>
            <li><a href="#">University Website</a></li>
            <li><a href="#">Online Results</a></li>
            <li><a href="#">Library Portal</a></li>
        </ul>
        
        <h3>Upcoming Events</h3>
        <p>Tech Fest: <time datetime="2026-04-20">April 20, 2026</time></p>
    </aside>

    <footer>
        <p>&copy; <time datetime="2026">2026</time> Mandsaur University. All Rights Reserved.</p>
        <address>
            Rewas Dewda Road, Mandsaur, MP 458001<br>
            Email: <a href="mailto:bca@mandsauruniversity.edu.in">bca@mandsauruniversity.edu.in</a>
        </address>
    </footer>

</body>
</html>
```

---

## 4. The `<details>` and `<summary>` Tags

Creates collapsible/expandable content — no JavaScript needed!

```html
<details>
    <summary>What is HTML?</summary>
    <p>HTML stands for HyperText Markup Language. It is used to structure web content.</p>
</details>

<details>
    <summary>What is CSS?</summary>
    <p>CSS stands for Cascading Style Sheets. It is used to style HTML elements.</p>
</details>
```

---

## Practice Exercise

Convert the department page from Day 6 (which used `<div>` tags) into a fully semantic HTML5 page:
1. Replace `<div>` sections with `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`
2. Add `<figure>` and `<figcaption>` for images
3. Use `<time>` for dates
4. Create an FAQ section using `<details>` and `<summary>`
5. Add a sidebar (`<aside>`) with quick links

---

## Summary

| Element | Purpose |
|---------|---------|
| `<header>` | Page/section header |
| `<nav>` | Navigation |
| `<main>` | Primary content (only 1) |
| `<article>` | Self-contained content |
| `<section>` | Thematic grouping |
| `<aside>` | Sidebar/tangential content |
| `<footer>` | Footer |
| `<figure>` + `<figcaption>` | Image + caption |
| `<details>` + `<summary>` | Expandable content |
| `<time>` | Machine-readable date/time |

---

*Day 14 of 55 | Unit 3 — HTML5 | Web Technology (25BCA060)*
