# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Local Development
To serve and preview the website locally, use Python's built-in HTTP server:
* Run local server: `python3 -m http.server 8000`
* Access local site: Open `http://localhost:8000` in your web browser.

### Deployment & Git Workflow
* Stage files: `git add <filename>`
* Commit changes: Use descriptive messages (e.g. `feat: add ...` or `style: update ...`)
* Push to live site: `git push origin main`

---

## Codebase Architecture

This project is a high-performance, single-page personal landing website (`yangss.xyz`). It has zero external package or build dependencies to guarantee instant loading and absolute portability.

### Key Files
* **`index.html`**: The entire application, containing layout (HTML5), styles (CSS3), and client-side interactions (vanilla JS).
* **`.gitignore`**: Excludes system files (such as `.DS_Store`) and editor directories.

### Structural Conventions
1. **Design System & Themes**:
   - Custom CSS variables (`:root`) define colors, borders, and animations.
   - Default theme is "Minimalist Light" (warm ivory/beige background `#faf8f5`).
   - Dark theme uses the `[data-theme="dark"]` selector (dark charcoal background `#121211`).
   - Theme variables must transition smoothly using `--transition-speed`.
2. **Behavior & Logic**:
   - Synchronizes automatically with the user's system color scheme (`prefers-color-scheme`).
   - Manual theme overrides are toggled using the header button and persist using `localStorage.setItem('theme', ...)`.
3. **Icons & Layout**:
   - Footer and contact icons are self-contained SVGs styled with CSS (`currentColor`) to scale cleanly and support dynamic theme colors.
   - Designed mobile-first, ensuring responsive centered scaling (max-width of `800px`).
