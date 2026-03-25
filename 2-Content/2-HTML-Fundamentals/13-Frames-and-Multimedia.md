# Day 13 — Frames & Multimedia Embedding

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 2 — HTML Fundamentals
🧪 **Lab Experiments:** 8, 9

---

## Learning Objectives

By the end of this session, students will be able to:
- Create framesets with multiple frames
- Control frame sizes and properties
- Embed audio and video using HTML tags
- Use `<iframe>` for embedding external content

---

## 1. Frames in HTML

> **Analogy:** Frames divide a browser window into **multiple panes**, like dividing a TV screen into picture-in-picture views. Each pane loads a separate HTML file independently.

### Frameset Structure

```html
<!-- Note: DOCTYPE must be Frameset for frames to work -->
<!DOCTYPE html>
<html>
<head>
    <title>Frames Demo</title>
</head>
<frameset cols="20%,60%,20%">
    <frame src="left.html" name="sidebar">
    <frame src="center.html" name="main">
    <frame src="right.html" name="remarks">
    <noframes>
        <p>Your browser does not support frames.</p>
    </noframes>
</frameset>
</html>
```

### Key Tags & Attributes

| Tag/Attribute | Purpose |
|--------------|---------|
| `<frameset>` | Replaces `<body>` — defines the frame layout |
| `cols` | Divide into vertical columns |
| `rows` | Divide into horizontal rows |
| `<frame>` | Individual frame (self-closing) |
| `src` | HTML file to load in the frame |
| `name` | Name of the frame (for targeting links) |
| `<noframes>` | Fallback for browsers that don't support frames |

### Frame Attributes

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `src` | Source file | `src="page.html"` |
| `name` | Frame name | `name="main"` |
| `scrolling` | Scrollbar | `yes`, `no`, `auto` |
| `noresize` | Prevent resizing | `noresize` |
| `frameborder` | Border visibility | `0` (hidden), `1` (shown) |
| `marginwidth` | Horizontal margin | `marginwidth="10"` |
| `marginheight` | Vertical margin | `marginheight="10"` |

### Targeting Links to Frames

```html
<!-- In left.html (sidebar) -->
<a href="about.html" target="main">About</a>
<a href="courses.html" target="main">Courses</a>
```
When clicked, these links load in the frame named `"main"` (the center frame).

> ⚠️ Frames (`<frameset>`, `<frame>`) are **deprecated in HTML5**. Use `<iframe>` or CSS layouts instead. We cover them because they're in the syllabus.

---

## 2. Inline Frames (`<iframe>`)

`<iframe>` embeds another HTML page **within** the current page (not deprecated).

```html
<!-- Embed another webpage -->
<iframe src="https://www.example.com" width="600" height="400" title="Example"></iframe>

<!-- Embed a YouTube video -->
<iframe width="560" height="315" 
    src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
    title="YouTube video" 
    frameborder="0" 
    allowfullscreen>
</iframe>

<!-- Embed Google Maps -->
<iframe src="https://www.google.com/maps/embed?pb=..." 
    width="600" height="450" 
    style="border:0;" 
    allowfullscreen="" 
    loading="lazy">
</iframe>
```

---

## 3. Audio in HTML

### HTML5 `<audio>` Tag

```html
<audio controls>
    <source src="music.mp3" type="audio/mpeg">
    <source src="music.ogg" type="audio/ogg">
    Your browser does not support the audio element.
</audio>
```

### Audio Attributes

| Attribute | Purpose |
|-----------|---------|
| `controls` | Show play/pause/volume controls |
| `autoplay` | Start playing automatically |
| `loop` | Repeat continuously |
| `muted` | Start muted |
| `preload` | `auto`, `metadata`, or `none` |

### Supported Audio Formats

| Format | MIME Type | Support |
|--------|-----------|---------|
| MP3 | `audio/mpeg` | All modern browsers |
| OGG | `audio/ogg` | Firefox, Chrome, Opera |
| WAV | `audio/wav` | Most browsers |

---

## 4. Video in HTML

### HTML5 `<video>` Tag

```html
<video width="640" height="360" controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Your browser does not support the video element.
</video>
```

### Video Attributes

| Attribute | Purpose |
|-----------|---------|
| `controls` | Show playback controls |
| `width` / `height` | Video dimensions |
| `autoplay` | Auto-start (requires `muted` in Chrome) |
| `loop` | Repeat video |
| `muted` | Start muted |
| `poster` | Image shown before video plays |

```html
<video width="640" height="360" controls poster="thumbnail.jpg" muted>
    <source src="intro.mp4" type="video/mp4">
</video>
```

---

## 5. Embedding YouTube Videos

```html
<!-- Steps: Go to YouTube → Share → Embed → Copy code -->
<iframe width="560" height="315" 
    src="https://www.youtube.com/embed/VIDEO_ID" 
    title="Video Title" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen>
</iframe>
```

---

## Practical Session

### 🧪 Lab Experiment 8: Three-Frame Layout

**Objective:** Create a page divided into 3 frames — left (20%) for navigation, center (60%) for content, and right (20%) for remarks.

**File: `frameset.html`**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Three Frame Layout</title>
</head>
<frameset cols="20%,60%,20%">
    <frame src="nav.html" name="sidebar" scrolling="auto">
    <frame src="welcome.html" name="main" scrolling="auto">
    <frame src="remarks.html" name="remarks" scrolling="auto">
    <noframes>
        <p>Your browser does not support frames. Please use a modern browser.</p>
    </noframes>
</frameset>
</html>
```

**File: `nav.html`**
```html
<!DOCTYPE html>
<html>
<head><title>Navigation</title></head>
<body bgcolor="#E3F2FD" style="font-family: Arial;">
    <h3>Contents</h3>
    <p><a href="welcome.html" target="main">Home</a></p>
    <p><a href="about.html" target="main">About</a></p>
    <p><a href="courses.html" target="main">Courses</a></p>
    <p><a href="faculty.html" target="main">Faculty</a></p>
    <p><a href="contact.html" target="main">Contact</a></p>
</body>
</html>
```

**File: `welcome.html`**
```html
<!DOCTYPE html>
<html>
<head><title>Welcome</title></head>
<body style="font-family: Arial; padding: 20px;">
    <h1>Welcome to BCA Department</h1>
    <p>Click on the links in the left panel to navigate.</p>
    <p>This is the main content area where pages will be displayed.</p>
</body>
</html>
```

**File: `remarks.html`**
```html
<!DOCTYPE html>
<html>
<head><title>Remarks</title></head>
<body bgcolor="#FFF9C4" style="font-family: Arial;">
    <h3>Remarks</h3>
    <p><em>Updated: April 2026</em></p>
    <p>New admissions open!</p>
    <p>Lab hours: 9 AM - 5 PM</p>
</body>
</html>
```

---

### 🧪 Lab Experiment 9: Embed Audio and Video

**Objective:** Create a multimedia-rich webpage with embedded audio and video.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multimedia Gallery</title>
</head>
<body style="font-family: Arial; max-width: 800px; margin: 0 auto; padding: 20px;">

    <h1 align="center">Multimedia Gallery</h1>
    <hr>

    <!-- Audio Section -->
    <h2>🎵 Audio Player</h2>
    <p>Listen to the campus anthem:</p>
    <audio controls style="width: 100%;">
        <source src="anthem.mp3" type="audio/mpeg">
        <source src="anthem.ogg" type="audio/ogg">
        Your browser does not support the audio element.
    </audio>
    
    <br><br>

    <!-- Video Section -->
    <h2>🎬 Video Player</h2>
    <p>Watch our campus tour:</p>
    <video width="100%" controls poster="https://via.placeholder.com/800x450?text=Campus+Tour">
        <source src="campus-tour.mp4" type="video/mp4">
        <source src="campus-tour.webm" type="video/webm">
        Your browser does not support the video element.
    </video>

    <br><br>

    <!-- Embedded YouTube Video -->
    <h2>📺 Embedded YouTube Video</h2>
    <p>HTML Tutorial for Beginners:</p>
    <div align="center">
        <iframe width="560" height="315" 
            src="https://www.youtube.com/embed/qz0aGYrrlhU" 
            title="HTML Tutorial" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen>
        </iframe>
    </div>

    <hr>
    <p align="center"><em>Unit 2 Complete! Next: HTML5 &rarr;</em></p>

</body>
</html>
```

---

## Practice Exercise

1. Create a frame-based website with:
   - Top frame (header): 15% height
   - Left frame (menu): 20% width
   - Center frame (content): remaining space
   - Use nested framesets: `rows` for top/bottom, then `cols` for left/right

2. Create a multimedia page with:
   - At least 2 audio players
   - 1 local video player with poster
   - 1 embedded YouTube video
   - Proper fallback text for unsupported browsers

---

## Summary

| Concept | Key Takeaway |
|---------|-------------|
| `<frameset>` | Divides window into frames (deprecated in HTML5) |
| `<frame>` | Individual pane loading a separate HTML file |
| `target="frameName"` | Opens link in a specific frame |
| `<iframe>` | Embeds content inline (NOT deprecated) |
| `<audio>` | HTML5 audio player with controls |
| `<video>` | HTML5 video player with controls |
| `<source>` | Provides multiple format options for audio/video |

---

**🎉 Unit 2 Complete!** Starting Day 14, we move to **Unit 3: HTML5** — semantic elements, new form types, APIs, and more.

---

*Day 13 of 55 | Unit 2 — HTML Fundamentals | Web Technology (25BCA060)*
