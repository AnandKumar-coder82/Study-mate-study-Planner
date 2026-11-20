# 📚 StudyFlow — Smart Student Study Planner

> **Academic Collaborative Web Application Project**  
> Developed for the collaborative web development course assessing students' ability to design, develop, and deploy a responsive, accessible, and interactive web application using pure **Semantic HTML5, CSS3, and Modern JavaScript (ES6+)**.

---

## 🌟 Live Demo & Repository
- **GitHub Repository**: `https://github.com/<username>/study-planner`
- **GitHub Pages Live Deployment**: `https://<username>.github.io/study-planner/`

---

## 📋 Table of Contents
1. [Project Overview & Key Objectives](#project-overview--key-objectives)
2. [Team Roles & Collaborative Division of Labor](#team-roles--collaborative-division-of-labor)
3. [Key Features](#key-features)
4. [Course Rubric & Concepts Applied](#course-rubric--concepts-applied)
5. [Architecture & Code Organization](#architecture--code-organization)
6. [Browser APIs Demonstrated](#browser-apis-demonstrated)
7. [Debugging Techniques & Defensive Engineering](#debugging-techniques--defensive-engineering)
8. [Step-by-Step GitHub Pages Deployment Guide](#step-by-step-github-pages-deployment-guide)
9. [Local Development & Testing](#local-development--testing)

---

## 🎯 Project Overview & Key Objectives
**StudyFlow** is a modern, responsive, and distraction-free study management web application designed specifically for students. It combines task prioritization, weekly scheduling, Pomodoro deep-focus intervals, and data-driven study analytics into a single cohesive, client-side dashboard with zero external framework dependencies.

### Primary Objectives:
- Demonstrate semantic and accessible HTML5 markup (`<header>`, `<nav>`, `<aside>`, `<main>`, `<section>`, `<article>`, `<dialog>`).
- Implement modern responsive CSS3 layouts using Flexbox, CSS Grid, CSS Custom Properties (Light/Dark themes), and a dedicated `@media print` stylesheet.
- Leverage vanilla JavaScript (ES6+) to build modular state management, dynamic DOM rendering, and comprehensive form validation.
- Utilize modern Browser APIs: `localStorage`, `Notification API`, `Web Audio API` (native audio synthesizer chime), `Drag and Drop API`, `Canvas API`, and `Blob/File API`.
- Deploy seamlessly to GitHub Pages as a high-performance static web application.

---

## 👥 Team Roles & Collaborative Division of Labor
This project was collaboratively designed, developed, and tested by a group of **three students**:

| Team Member | Role & Ownership | Core Responsibilities & Contributions |
| :--- | :--- | :--- |
| **Student 1** | **Lead UI/UX & Responsive Semantic HTML/CSS Architect** | • Designed the semantic HTML5 structure (`index.html`), ARIA attributes, and accessible `<dialog>` modals.<br>• Authored `main.css`, `components.css`, and `responsive.css`.<br>• Implemented CSS Custom Properties for dynamic Light and Dark mode theme switching.<br>• Built the responsive mobile drawer sidebar navigation and `@media print` print styles for printing weekly timetables. |
| **Student 2** | **Client-Side Logic & State Architecture Engineer** | • Architected the modular JavaScript data flow in `app.js` and `storage.js`.<br>• Developed persistent storage routines with sample starter datasets for grading demonstration.<br>• Built the Task CRUD engine (`tasks.js`), multi-attribute filtering (subject, priority), and debounced search.<br>• Implemented client-side constraint form validation with inline visual error messaging. |
| **Student 3** | **Interactive Web Development, Browser APIs & Deployment Specialist** | • Developed the interactive Pomodoro Focus Timer (`timer.js`) with SVG circular progress countdown.<br>• Built the HTML5 Drag-and-Drop Kanban Board with interactive status dropzones.<br>• Implemented Browser APIs: Web Audio API sound chime synthesizer, Desktop Notifications, and JSON/CSV backup import/export.<br>• Programmed pure HTML5 Canvas charts (`analytics.js`) and managed Git version control and GitHub Pages deployment. |

---

## ✨ Key Features

### 1. 📊 Central Student Command Dashboard
- High-level KPI metric cards: Tasks Completed %, Today's Focus Minutes, Upcoming 48-Hour Deadlines, and Course Counts.
- Dynamic Today's Priority Agenda featuring instant "Start Focus" shortcuts.
- Motivational banner quotes and active study streak tracking.

### 2. 📝 Task Board & Dual Views (List & Kanban)
- **Table List View**: Clean, sortable tabular view displaying task title, subject badge, priority pill, due date status, and estimated study duration.
- **Kanban Board View**: Interactive drag-and-drop columns (`To Do`, `In Progress`, `Completed`) leveraging the native HTML5 Drag and Drop API.
- **Search & Filter Toolbar**: Real-time debounced text search, filter by subject/course, filter by priority, and sort by due date or priority.

### 3. 📅 Weekly Schedule & Printable Timetable
- 7-day visual calendar grid mapping all assignments to their respective deadlines.
- Previous / Next week navigation.
- Built-in **"Print Schedule"** action powered by a dedicated `@media print` CSS stylesheet for paper agendas.

### 4. ⏱️ Integrated Pomodoro Focus Timer
- 3 distinct intervals: **Focus (25m)**, **Short Break (5m)**, and **Long Break (15m)** with customizable durations.
- Animated SVG circular progress ring visualizing time elapsed.
- Header countdown capsule and browser tab title reflection (e.g. `(24:15) Focus — StudyFlow`).
- Ability to link the active focus session directly to any pending study task.
- Dual sound alert (Web Audio synthesizer) and desktop browser notification when intervals complete.

### 5. 📈 Data-Driven Canvas Analytics (Zero External Libraries)
- **Subject Donut Chart**: Rendered dynamically using pure HTML5 2D Canvas context, showing proportional hours dedicated per course.
- **Weekly Bar Chart**: High-DPI canvas bar chart illustrating daily focus minutes throughout the week with today's column highlighted.
- **Study Session History Log**: Chronological log of all completed Pomodoro sessions with one-click clear option.

### 6. 💾 Backup, Export & Portability
- **Export Backup (JSON)**: Full state export.
- **Export Tasks (CSV)**: Generates spreadsheet-compatible CSV via `Blob` and `encodeURI`.
- **Import Backup (JSON)**: Upload previously exported backup via `FileReader`.
- **Reset to Sample Data**: Quick restoration of demo student tasks for grading and evaluation.

---

## 📚 Course Rubric & Concepts Applied

### 1. HTML Fundamentals & Semantic HTML
- Valid `<!DOCTYPE html>` with proper metadata (viewport, theme-color, UTF-8, SEO description).
- Consistent usage of semantic tags: `<header>`, `<nav>`, `<aside>`, `<main>`, `<section>`, `<article>`, `<dialog>`, `<figure>`, `<time>`.
- Accessible markup: WCAG compliant skip-to-content link, `aria-label`, `aria-describedby`, `aria-haspopup`, and `role` attributes.

### 2. Forms & Form Validation
- Rich input controls: `text`, `date`, `time`, `number`, `select`, `textarea`, and hidden ID fields.
- Real-time client-side validation using JavaScript:
  - Dynamic error messages toggling (`.is-invalid` class).
  - Validation rules: Minimum character length for task titles, valid future/due dates, and conditional required inputs when "Custom Subject" is chosen.
  - Immediate clearance of error states upon corrected user typing.

### 3. Cascading Style Sheets (CSS3)
- **CSS Custom Properties (Variables)**: Centralized design system with tokens for colors, shadows, border-radii, and spacing.
- **Light & Dark Theme Engine**: System preference detection (`prefers-color-scheme`) with persistent manual toggle stored in `localStorage`.
- **Modern Responsive Layouts**: CSS Grid (`grid-template-columns: repeat(...)`) and Flexbox layouts.
- **Print Stylesheet (`@media print`)**: Strips out navigation, buttons, and backgrounds to format clean printed timetables.
- **Micro-Interactions**: Smooth cubic-bezier transitions, hover elevations, and SVG animations.

### 4. JavaScript Fundamentals & Code Organization
- Written in modern **ECMAScript 6+** (ES6 arrow functions, object destructuring, template literals, `Set`, array methods like `.filter()`, `.map()`, `.reduce()`).
- Modular architecture using the **IIFE / Revealing Module Pattern** ensuring zero global namespace pollution:
  - `Utils`: Utility functions, date formatters, audio synthesis, toasts, debounce.
  - `Storage`: Persistence manager, import/export logic, seed data.
  - `Tasks`: CRUD logic, validation, table and kanban renderers.
  - `Timer`: Pomodoro interval state machine, notifications, SVG updates.
  - `Analytics`: Canvas geometry, bar/donut drawing, streak calculation.
  - `App`: Main orchestrator, hash routing, theme switching, modal handling.

### 5. Interactive Web Development & DOM Manipulation
- Single-page application (SPA) architecture with hash routing (`#dashboard`, `#tasks`, `#timetable`, `#pomodoro`, `#analytics`).
- Efficient DOM updates with event delegation for table checkboxes and action buttons.
- Drag and Drop API implementation with custom visual feedback (`drag-over`, `dragging`).

### 6. Browser APIs Implemented
- **Web Storage API (`localStorage`)**: Saves tasks, settings, theme, and session history across browser restarts.
- **Notification API**: Requests user permission and dispatches native operating system notifications when focus sessions finish.
- **Web Audio API**: Uses `AudioContext` to synthesize gentle two-tone sine-wave chimes on timer completion (requires zero external MP3/WAV assets).
- **HTML5 Canvas 2D API**: High-DPI crisp rendering of Donut and Bar charts with custom arc and rounded-rect math.
- **HTML5 Drag and Drop API**: Native draggable cards and dropzones for kanban status management.
- **File API & Blob API**: Seamless client-side JSON/CSV file generation and local file reading.

---

## 🏗️ Architecture & Code Organization

```
study-planner/
│
├── index.html               # Main semantic HTML document with all view templates & modal
│
├── css/
│   ├── main.css             # Theme variables (Light/Dark), reset, typography & core layouts
│   ├── components.css       # Cards, table, Kanban, timer, timetable & modal styles
│   └── responsive.css       # Mobile/tablet media queries & @media print styles
│
├── js/
│   ├── utils.js             # Helper functions, Web Audio synthesizer chime, toasts, debounce
│   ├── storage.js           # LocalStorage CRUD, default starter data, JSON/CSV export/import
│   ├── tasks.js             # Task management, form validation, Kanban drag-and-drop, timetable
│   ├── timer.js             # Pomodoro focus timer, circular SVG countdown, notification triggers
│   ├── analytics.js         # Vanilla HTML5 Canvas charts (Donut & Bar), streak counter
│   └── app.js               # Main bootstrap, navigation router, theme toggle & shortcuts
│
└── README.md                # Project documentation, group roles, rubric matrix & deployment guide
```

---

## 🛠️ Debugging Techniques & Defensive Engineering
During development, the team utilized several key debugging and defensive programming practices:
1. **Defensive Storage Parsing**: All `localStorage.getItem()` calls are wrapped inside `try...catch` blocks to protect against corrupted JSON data or disabled storage.
2. **XSS Prevention**: User inputs are passed through `Utils.escapeHtml()` before rendering to prevent malicious HTML/script injection.
3. **High-DPI Retina Canvas Scaling**: Canvas charts calculate `window.devicePixelRatio` and scale coordinate systems dynamically so charts remain ultra-sharp on 4K, Retina, and mobile screens.
4. **Debounced Event Listeners**: The task search input is throttled through a 200ms debounce helper to prevent excessive DOM reflows during rapid keystrokes.
5. **No 404 External Asset Failures**: Sounds are synthesized directly via Web Audio oscillator math, and SVG icons are embedded inline, guaranteeing zero missing asset failures on deployment.

---

## 🚀 Step-by-Step GitHub Pages Deployment Guide

Because **StudyFlow** is built entirely with client-side HTML, CSS, and JavaScript, it requires **zero build steps, compilers, or server configuration** to deploy on GitHub Pages.

### Step 1: Initialize Git Repository
In your local project folder:
```bash
git init
git add .
git commit -m "feat: initial commit of complete StudyFlow web application"
```

### Step 2: Push to GitHub
Create a new public repository on GitHub named `study-planner` (or any preferred name), then run:
```bash
git branch -M main
git remote add origin https://github.com/<your-username>/study-planner.git
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to your repository on [GitHub](https://github.com).
2. Click **Settings** (top navigation tab).
3. On the left sidebar, click **Pages** (under "Code and automation").
4. Under **Build and deployment** > **Source**, select **Deploy from a branch**.
5. Under **Branch**, select `main` and folder `/ (root)`.
6. Click **Save**.

### Step 4: Access Your Live Web App
Within 1 to 2 minutes, GitHub will publish your site. Your live application will be accessible at:
```
https://<your-username>.github.io/study-planner/
```

---

## 💻 Local Development & Testing
To preview and test the project locally:

1. Clone or open the project folder `study-planner`.
2. Open `index.html` directly in any modern web browser (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).
3. Alternatively, launch a local development server using any of the following:
   - **VS Code**: Right-click `index.html` and click **"Open with Live Server"**.
   - **Node.js (npx)**: Run `npx serve .` in the terminal.
   - **Python**: Run `python -m http.server 8000` and visit `http://localhost:8000`.

---

## ⌨️ Accessibility & Keyboard Shortcuts
- `N` or `n`: Quickly opens the **Add Study Task** modal from anywhere.
- `Space`: Starts or pauses the **Pomodoro Focus Timer** (when on the Pomodoro view).
- `Escape`: Closes open modals or the mobile sidebar drawer.
- `Tab`: Sequential accessible navigation through skip links, buttons, and form inputs.

---

## 📄 License & Academic Integrity
This project was developed for academic assessment purposes. All code is original and adheres to collaborative web development standards. Feel free to use, study, and expand upon this codebase.
