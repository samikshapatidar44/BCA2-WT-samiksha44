# Day 34 — Bootstrap Navigation & Navbar

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 6 — Bootstrap
🧪 **Lab Experiment:** 25

---

## Learning Objectives

By the end of this session, students will be able to:
- Create responsive Bootstrap navbar with brand, links, and dropdown
- Add a hamburger menu for mobile screens
- Build breadcrumb and pagination navigation
- Use Bootstrap nav tabs and pills

---

## 1. Bootstrap Navbar

### Basic Responsive Navbar

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <!-- Brand -->
        <a class="navbar-brand" href="#">MU — BCA</a>
        
        <!-- Hamburger button (mobile) -->
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" 
                data-bs-target="#mainNav">
            <span class="navbar-toggler-icon"></span>
        </button>
        
        <!-- Collapsible links -->
        <div class="collapse navbar-collapse" id="mainNav">
            <ul class="navbar-nav me-auto">
                <li class="nav-item">
                    <a class="nav-link active" href="#">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">About</a>
                </li>
                
                <!-- Dropdown -->
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" data-bs-toggle="dropdown">
                        Courses
                    </a>
                    <ul class="dropdown-menu">
                        <li><a class="dropdown-item" href="#">Web Technology</a></li>
                        <li><a class="dropdown-item" href="#">Data Structures</a></li>
                        <li><hr class="dropdown-divider"></li>
                        <li><a class="dropdown-item" href="#">All Courses</a></li>
                    </ul>
                </li>
                
                <li class="nav-item">
                    <a class="nav-link" href="#">Contact</a>
                </li>
            </ul>
            
            <!-- Search form -->
            <form class="d-flex" role="search">
                <input class="form-control me-2" type="search" placeholder="Search">
                <button class="btn btn-outline-light" type="submit">Search</button>
            </form>
        </div>
    </div>
</nav>
```

### Navbar Color Schemes

| Classes | Appearance |
|---------|-----------|
| `navbar-dark bg-dark` | White text on dark background |
| `navbar-dark bg-primary` | White text on blue background |
| `navbar-light bg-light` | Dark text on light background |
| `bg-transparent` | Transparent background |

---

## 2. Nav Tabs & Pills

### Tabs

```html
<ul class="nav nav-tabs" id="myTab">
    <li class="nav-item">
        <button class="nav-link active" data-bs-toggle="tab" data-bs-target="#html">HTML</button>
    </li>
    <li class="nav-item">
        <button class="nav-link" data-bs-toggle="tab" data-bs-target="#css">CSS</button>
    </li>
    <li class="nav-item">
        <button class="nav-link" data-bs-toggle="tab" data-bs-target="#js">JavaScript</button>
    </li>
</ul>
<div class="tab-content p-3 border border-top-0">
    <div class="tab-pane fade show active" id="html">
        <p>HTML provides the structure of web pages.</p>
    </div>
    <div class="tab-pane fade" id="css">
        <p>CSS controls the appearance and layout.</p>
    </div>
    <div class="tab-pane fade" id="js">
        <p>JavaScript adds interactivity.</p>
    </div>
</div>
```

### Pills (Rounded Tab Style)

```html
<ul class="nav nav-pills">
    <li class="nav-item">
        <a class="nav-link active" href="#">Active</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
    </li>
</ul>
```

---

## 3. Breadcrumb & Pagination

### Breadcrumb

```html
<nav aria-label="breadcrumb">
    <ol class="breadcrumb">
        <li class="breadcrumb-item"><a href="#">Home</a></li>
        <li class="breadcrumb-item"><a href="#">Courses</a></li>
        <li class="breadcrumb-item active">Web Technology</li>
    </ol>
</nav>
```

### Pagination

```html
<nav>
    <ul class="pagination justify-content-center">
        <li class="page-item disabled"><a class="page-link" href="#">Previous</a></li>
        <li class="page-item active"><a class="page-link" href="#">1</a></li>
        <li class="page-item"><a class="page-link" href="#">2</a></li>
        <li class="page-item"><a class="page-link" href="#">3</a></li>
        <li class="page-item"><a class="page-link" href="#">Next</a></li>
    </ul>
</nav>
```

---

## Practical Session

### 🧪 Lab Experiment 25: Complete Navigation Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Navigation</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary sticky-top">
        <div class="container">
            <a class="navbar-brand fw-bold" href="#">🎓 Mandsaur University</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#topNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="topNav">
                <ul class="navbar-nav me-auto">
                    <li class="nav-item"><a class="nav-link active" href="#">Home</a></li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" data-bs-toggle="dropdown">Departments</a>
                        <ul class="dropdown-menu">
                            <li><a class="dropdown-item" href="#">BCA</a></li>
                            <li><a class="dropdown-item" href="#">BBA</a></li>
                            <li><a class="dropdown-item" href="#">B.Tech</a></li>
                            <li><hr class="dropdown-divider"></li>
                            <li><a class="dropdown-item" href="#">View All</a></li>
                        </ul>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" data-bs-toggle="dropdown">BCA Courses</a>
                        <ul class="dropdown-menu">
                            <li><a class="dropdown-item" href="#">Web Technology</a></li>
                            <li><a class="dropdown-item" href="#">Data Structures</a></li>
                            <li><a class="dropdown-item" href="#">Mathematics</a></li>
                        </ul>
                    </li>
                    <li class="nav-item"><a class="nav-link" href="#">Faculty</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Contact</a></li>
                </ul>
                <form class="d-flex">
                    <input class="form-control me-2" type="search" placeholder="Search...">
                    <button class="btn btn-outline-light" type="submit">Search</button>
                </form>
            </div>
        </div>
    </nav>

    <div class="container my-4">

        <!-- Breadcrumb -->
        <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
                <li class="breadcrumb-item"><a href="#">Home</a></li>
                <li class="breadcrumb-item"><a href="#">BCA</a></li>
                <li class="breadcrumb-item"><a href="#">Semester II</a></li>
                <li class="breadcrumb-item active">Web Technology</li>
            </ol>
        </nav>

        <h2>Web Technology — Course Content</h2>

        <!-- Tabs -->
        <ul class="nav nav-tabs mt-4" id="unitTabs">
            <li class="nav-item">
                <button class="nav-link active" data-bs-toggle="tab" data-bs-target="#unit1">Unit 1</button>
            </li>
            <li class="nav-item">
                <button class="nav-link" data-bs-toggle="tab" data-bs-target="#unit2">Unit 2</button>
            </li>
            <li class="nav-item">
                <button class="nav-link" data-bs-toggle="tab" data-bs-target="#unit3">Unit 3</button>
            </li>
            <li class="nav-item">
                <button class="nav-link" data-bs-toggle="tab" data-bs-target="#unit4">Unit 4</button>
            </li>
            <li class="nav-item">
                <button class="nav-link" data-bs-toggle="tab" data-bs-target="#unit5">Unit 5</button>
            </li>
        </ul>
        <div class="tab-content border border-top-0 rounded-bottom p-4 bg-white mb-4">
            <div class="tab-pane fade show active" id="unit1">
                <h5>Internet Technology</h5>
                <p>History of Internet, TCP/IP, DNS, World Wide Web, HTTP/HTTPS</p>
                <span class="badge bg-primary">5 Days</span>
                <span class="badge bg-success">Theory Only</span>
            </div>
            <div class="tab-pane fade" id="unit2">
                <h5>HTML Fundamentals</h5>
                <p>HTML structure, text formatting, links, images, tables, lists, frames</p>
                <span class="badge bg-primary">8 Days</span>
                <span class="badge bg-info">Theory + Lab</span>
            </div>
            <div class="tab-pane fade" id="unit3">
                <h5>HTML5</h5>
                <p>Semantic elements, new form inputs, Canvas, SVG, APIs, responsive design</p>
                <span class="badge bg-primary">5 Days</span>
                <span class="badge bg-info">Theory + Lab</span>
            </div>
            <div class="tab-pane fade" id="unit4">
                <h5>CSS</h5>
                <p>Selectors, Box Model, Flexbox, Grid, Animations, Transitions</p>
                <span class="badge bg-primary">7 Days</span>
                <span class="badge bg-info">Theory + Lab</span>
            </div>
            <div class="tab-pane fade" id="unit5">
                <h5>Bootstrap</h5>
                <p>Grid system, components, navbar, forms, carousel, responsive utilities</p>
                <span class="badge bg-primary">7 Days</span>
                <span class="badge bg-info">Theory + Lab</span>
            </div>
        </div>

        <!-- Pagination -->
        <nav aria-label="Page navigation">
            <ul class="pagination justify-content-center">
                <li class="page-item disabled"><a class="page-link" href="#">&laquo; Previous</a></li>
                <li class="page-item active"><a class="page-link" href="#">1</a></li>
                <li class="page-item"><a class="page-link" href="#">2</a></li>
                <li class="page-item"><a class="page-link" href="#">3</a></li>
                <li class="page-item"><a class="page-link" href="#">Next &raquo;</a></li>
            </ul>
        </nav>
    </div>

    <!-- Footer -->
    <footer class="bg-dark text-white text-center py-3">
        <p class="mb-0">&copy; 2026 Mandsaur University — All Rights Reserved</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

---

## Summary

| Component | Key Classes |
|-----------|------------|
| Navbar | `navbar`, `navbar-expand-lg`, `navbar-dark bg-primary` |
| Toggler | `navbar-toggler`, `collapse navbar-collapse` |
| Dropdown | `dropdown`, `dropdown-toggle`, `dropdown-menu` |
| Tabs | `nav nav-tabs`, `tab-content`, `tab-pane` |
| Breadcrumb | `breadcrumb`, `breadcrumb-item` |
| Pagination | `pagination`, `page-item`, `page-link` |

---

*Day 34 of 55 | Unit 6 — Bootstrap | Web Technology (25BCA060)*
