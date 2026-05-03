# ExamWiki Flagship Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a production-grade, 2-column documentation site for CST362 Python notes with embedded data and high-speed search.

**Architecture:** Textbook Monolith. All content is stored in `data.js` and rendered on page load. A wider Left Sidebar handles both global (Module) and local (Topic) navigation, auto-updating on scroll.

**Tech Stack:** Vanilla HTML/CSS/JS, Instrument Serif (Italic), DM Sans, JetBrains Mono.

---

### Task 1: Scaffolding & Directory Setup

**Files:**
- Create: `ExamWiki/index.html`
- Create: `ExamWiki/styles.css`
- Create: `ExamWiki/data.js`
- Create: `ExamWiki/app.js`

- [ ] **Step 1: Initialize local directory and git**
```powershell
mkdir ExamWiki; cd ExamWiki; git init
```

- [ ] **Step 2: Create basic HTML skeleton**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>ExamWiki — CST362</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body class="light-theme">
    <div id="progress-bar"></div>
    <header id="site-header"></header>
    <div class="layout-container">
        <aside id="sidebar"></aside>
        <main id="content-well"></main>
    </div>
    <script src="data.js"></script>
    <script src="app.js"></script>
</body>
</html>
```

- [ ] **Step 3: Commit scaffold**
```bash
git add .
git commit -m "chore: initial scaffold"
```

---

### Task 2: Data Architecture (The Monolith)

**Files:**
- Modify: `ExamWiki/data.js`

- [ ] **Step 1: Embed full content for all 5 Modules**
Include all text from `notes/Module_1_Notes.md` through `notes/Module_5_Notes.md`. Ensure each section has an `id`, `title`, `badge` (HIGH/MED/LOW), and `summary`.

```javascript
const SYLLABUS = [
    {
        id: "module-1",
        title: "Module 1: Algorithms & Iteration",
        topics: [
            {
                id: "m1-t1",
                title: "Standard Number Algorithms",
                badge: "HIGH",
                summary: "Mastering Prime, Armstrong, and Factorial logic with digit extraction.",
                content: `... full content of Topic 1 ...`
            }
            // ... rest of Module 1 topics
        ]
    }
    // ... modules 2, 3, 4, 5
];
```

- [ ] **Step 2: Verify data integrity**
Check that no sections were truncated and all code blocks are preserved.

- [ ] **Step 3: Commit data**
```bash
git add ExamWiki/data.js
git commit -m "feat: embed full 5-module syllabus data"
```

---

### Task 3: Design System & 2-Column Layout

**Files:**
- Modify: `ExamWiki/styles.css`
- Modify: `ExamWiki/index.html`

- [ ] **Step 1: Define CSS Variables (Warm Paper / Deep Midnight)**
```css
:root {
    --bg: #F5F4F0; --surface: #FFFFFF; --border: #E3E2DA;
    --text: #1C1C1A; --muted: #6B6A62; --accent: #2952CC;
    --badge-high: #FEE2E2; --badge-high-text: #991B1B;
}
body.dark-theme {
    --bg: #09090B; --surface: #121214; --border: #27272A;
    --text: #F4F4F5; --accent: #6681F0;
}
```

- [ ] **Step 2: Implement 2-Column Grid**
```css
.layout-container {
    display: grid;
    grid-template-columns: 320px 1fr;
    max-width: 1400px;
    margin: 0 auto;
}
#sidebar { position: sticky; top: 52px; height: calc(100vh - 52px); overflow-y: auto; }
#content-well { max-width: 800px; margin: 0 auto; padding: 48px; }
```

- [ ] **Step 3: Commit styles**
```bash
git add .
git commit -m "style: implement 2-column responsive layout and theme tokens"
```

---

### Task 4: Dynamic Rendering Engine

**Files:**
- Modify: `ExamWiki/app.js`

- [ ] **Step 1: Render Sidebar Tree**
Loop through `SYLLABUS` and create Module groups with Topic sub-items.

- [ ] **Step 2: Render Content Monolith**
Loop through `SYLLABUS` and render every Module and Topic as a continuous vertical scroll in the `#content-well`.

- [ ] **Step 3: Implement Module Accordions**
Wrap each Module in a `<details>` element that is open by default.

- [ ] **Step 4: Commit engine**
```bash
git add ExamWiki/app.js
git commit -m "feat: dynamic rendering engine for monolith content"
```

---

### Task 5: High-End Interactive Features

**Files:**
- Modify: `ExamWiki/app.js`
- Modify: `ExamWiki/styles.css`

- [ ] **Step 1: IntersectionObserver for Navigation**
Track which H3 is in the viewport and update the sidebar's `.active` state and the header breadcrumb.

- [ ] **Step 2: ⌘K Command Palette**
Implement a modal search that filters `SYLLABUS` headings and summaries.

- [ ] **Step 3: Code Block Polish**
Add a "Copy" button header to every `pre` block with feedback (`✓ Copied`).

- [ ] **Step 4: Theme Toggle & Reading Progress**
Add the fixed progress bar and the sun/moon toggle with physical scaling (`scale 0.97`).

- [ ] **Step 5: Commit features**
```bash
git add .
git commit -m "feat: search modal, scroll-tracking, and copy buttons"
```

---

### Task 6: Deployment & Final Verification

**Files:**
- Create: `ExamWiki/README.md`

- [ ] **Step 1: Build GitHub Repository**
```bash
gh repo create ExamWiki --public --source=. --remote=origin --push
```

- [ ] **Step 2: Verify site locally**
Check for console errors and ensure all 5 modules are fully readable.

- [ ] **Step 3: Final push**
```bash
git push origin master
```
