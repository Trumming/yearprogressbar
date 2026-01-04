# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page HTML application that displays a visual year progress tracker. The application is entirely self-contained in `index.html` - there are no build steps, external dependencies beyond Google Fonts, or backend services.

## Architecture

### Single-File Structure
The entire application lives in `index.html` with inline CSS (`<style>`), inline JavaScript (`<script>`), and embedded data:

- **CSS (lines 10-400)**: Custom styling using CSS variables, monospace/serif typography, responsive grid layouts, and CSS animations
- **HTML (lines 402-477)**: Semantic structure with language selector, progress display, stats cards, and share functionality
- **JavaScript (lines 479-877)**: All application logic including translations, date calculations, animations, and image generation

### Key Components

**Translation System (lines 480-613)**
- Object-based i18n with 11 languages (EN, ZH-CN/TW, JA, KO, ES, FR, DE, AR, HI, PT)
- Each translation includes UI labels, button text, footer, and locale for date formatting
- Language preference persists in `localStorage`

**Progress Calculation (lines 640-674)**
- Calculates year completion percentage based on elapsed milliseconds from Jan 1
- Computes days passed and days remaining
- Updates hourly via `setInterval`
- Uses `requestAnimationFrame` for smooth percentage counter animation

**Image Generation (lines 709-838)**
- `generateProgressImage()` creates a downloadable PNG using Canvas API
- Replicates the HTML layout in canvas (1200x1200px @ 2x DPI)
- `downloadProgressImage()` handles blob creation and file download with naming convention `year-progress-{year}-{lang}.png`

### Design System

**Typography**: Google Fonts (Space Mono for UI, Playfair Display for headlines)
**Colors** (CSS variables):
- `--black: #0a0a0a`
- `--white: #f5f5f5`
- `--accent: #ff6b35`
- `--gray: #8a8a8a`

**Visual Style**: Brutalist design with thick borders (4px), hover effects with offset shadows, animated progress bar with pulsing accent edge

## Development

### Testing Changes
Simply open `index.html` in a browser - no server required. For live reloading during development:
```bash
# Python 3
python3 -m http.server 8000

# Node.js (if you have http-server installed)
npx http-server
```

### Adding New Languages
1. Add entry to `translations` object (line 480) following the structure:
   ```javascript
   'code': {
       title: '...',
       labelCurrentDate: '...',
       labelDaysPassed: '...',
       labelDaysRemaining: '...',
       labelCompleted: '...',
       labelToGo: '...',
       progressLabel: '...',
       shareButton: '...',
       footer: '...',
       locale: 'xx-XX'
   }
   ```
2. Add `<option>` to language selector dropdown (lines 419-431)

### Modifying Image Export
The `generateProgressImage()` function manually draws each element using Canvas 2D API. Changes to HTML/CSS layout will not automatically reflect in generated images - both must be updated separately to maintain consistency.

### Git Workflow
This repository has a pre-configured commit message in `.claude/settings.local.json`. When committing changes:
```bash
git add index.html
git commit -m "descriptive message"
```
