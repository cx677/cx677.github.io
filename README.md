# CET-4 Quest · 四级闯关

> **A gamified CET-4 English learning app with spaced repetition, learning analytics, and data export.**
> 5,200 lines of vanilla HTML/CSS/JS. No frameworks, no dependencies.

[![Deployed](https://img.shields.io/badge/deployed-GitHub%20Pages-brightgreen)](https://cx677.github.io)
[![Lines](https://img.shields.io/badge/code-5200%2B%20lines-blue)](index.html)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

---

## What It Does

A gamified CET-4 (College English Test Band 4) preparation app. Think Duolingo, but built from scratch by one person.

### Core Modules

```
┌─────────────────────────────────────────────────┐
│               CET-4 Quest                        │
│                                                  │
│  ┌──────────┐ ┌──────────┐ ┌──────────────────┐ │
│  │ 词汇闯关  │ │ 推理考场  │ │   AI 练笔        │ │
│  │ Flashcard │ │ Reading  │ │  Essay Practice  │ │
│  │ + Quiz    │ │ Comp.    │ │                  │ │
│  └─────┬────┘ └────┬─────┘ └────────┬─────────┘ │
│        │           │               │            │
│  ┌─────┴───────────┴───────────────┴─────────┐  │
│  │           Learning Engine                  │  │
│  │  · Ebbinghaus spaced repetition            │  │
│  │  · Adaptive difficulty (combo system)      │  │
│  │  · Progress persistence (localStorage)      │  │
│  └─────────────────────┬─────────────────────┘  │
│                        │                        │
│  ┌─────────────────────┴─────────────────────┐  │
│  │           Analytics Dashboard              │  │
│  │  · Radar chart (abilities)                 │  │
│  │  · Weekly study time chart                 │  │
│  │  · Day-over-day comparison                 │  │
│  │  · Streak tracking + achievements          │  │
│  └───────────────────────────────────────────┘  │
└─────────────────────────────────────────────────┘
```

### Technical Highlights

**Ebbinghaus Spaced Repetition Algorithm**
- Implements the forgetting curve: review at 1, 2, 4, 7, 15-day intervals
- Words tracked by mastery level per review cycle
- Adaptive: words you get wrong come back sooner

**State Management System**
```javascript
// Centralized state with localStorage persistence
State = {
  vocab: { groupUnlocked, wordMastered, reviewQueue },
  streak: { current, lastStudyDate },
  tasks: { daily, completed },
  achievements: [],
  activityLog: []
}
// Every action calls saveState() → JSON to localStorage
```

**Dashboard Analytics**
- Radar chart: visualizes abilities across 6 dimensions (词汇/阅读/听力/写作/语法/速度)
- Weekly bar chart: study time distribution
- Self-compare: today vs yesterday metrics
- Auto-generated daily snapshots for trend analysis

**Design System**
- 50+ CSS custom properties (design tokens)
- Dark/light theme toggle with smooth transitions
- Fully responsive (mobile + desktop)
- Keyboard shortcuts for power users
- Onboarding wizard for first-time users

---

## Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| Frontend | Vanilla HTML/CSS/JS (5,200 lines) | Zero dependencies, instant load |
| Persistence | localStorage | No backend needed, works offline |
| Charts | Canvas API (hand-drawn) | No chart library — built from scratch |
| Hosting | GitHub Pages | Free, HTTPS, global CDN |

**Deliberate choice**: No frameworks, no libraries. This demonstrates understanding of the platform itself — DOM manipulation, Canvas drawing, CSS architecture, state management patterns — rather than框架熟练度.

---

## Quick Start

```bash
# Just open the file
open index.html

# Or visit the deployed version
# https://cx677.github.io
```

No `npm install`. No build step. No server needed. This was a conscious engineering decision — the app works entirely client-side with localStorage persistence.

---

## Project Structure

```
cx677.github.io/
├── index.html    # Complete SPA (HTML + CSS + JS, 5,200 lines)
├── README.md     # This file
└── .gitignore
```

---

Built by [@cx677](https://github.com/cx677) · MIT License
