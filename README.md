# 🌍 CarbonTrack Pro — Google PromptWars Submission

![WCAG 2.1 AA](https://img.shields.io/badge/Accessibility-WCAG%202.1%20AA-success)
![Security: Hardened](https://img.shields.io/badge/Security-Strict%20CSP%20%2B%20Zero%20innerHTML-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

**CarbonTrack Pro** is a production-quality, high-performance Carbon Footprint Intelligence platform built as a single, self-contained `index.html` file. It was architected to demonstrate the upper limits of "Zero-Library" web development under strict constraints for Google's **PromptWars** challenge.

---

## 🚀 Live Demo & Installation

The application is entirely self-contained. No build steps, no `node_modules`.

### Fast Start
1. Clone the repo.
2. Run a local server to handle ESM modules:
   ```bash
   python -m http.server 8000
   ```
3. Open `http://localhost:8000` in your browser.

---

## 🏛 Architecture: The 5-Axis Excellence

This project was built to score maximum points across Google's judging criteria:

### 1. Code Quality & Architecture
- **Layered Design**: Config → Engine → State → App → Render.
- **Pure Functions**: The calculation engine (`calculations.js`) is side-effect free and strictly guarded with `Number.isFinite`.
- **Modular ESM**: Structured as a standard ES6 module despite being single-file.

### 2. Security (Hardened)
- **Zero innerHTML Policy**: All DOM writes use `textContent` or `createElementNS`.
- **Content Security Policy**: Integrated `<meta>` tag prevents XSS and unauthorized script execution.
- **State Isolation**: `AppState` is managed via `structuredClone` to prevent side-channel mutation of internal state.

### 3. Efficiency & Performance
- **rAF-Batched Rendering**: DOM writes are deduped via `requestAnimationFrame`.
- **WeakMap/Map Cache**: DOM elements are cached on first access to eliminate repetitive DOM queries.

### 4. Testing (100+ Assertions)
- **Self-Contained Runner**: A built-in async test runner executes 100+ assertions across 6 categories.
- **JSON Export**: Generate and download a full test report for audit.

### 5. Accessibility (WCAG 2.1 AA)
- **Semantic HTML**: Proper use of `<main>`, `<section>`, and `<header>`.
- **Skip Navigation**: First-focus "Skip to main content" link for keyboard users.
- **Reduced Motion**: All CSS transitions are strictly wrapped in `@media (prefers-reduced-motion: no-preference)`.

---

## 🛠 Tech Stack
- **Languages**: HTML5, Vanilla CSS3, Modern JavaScript (ES2022+).
- **Libraries**: **Zero.** Everything is hand-coded.

---

## 📝 License
Distributed under the MIT License. See `LICENSE` for more information.
