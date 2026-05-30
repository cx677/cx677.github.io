# CET-4 Quest · 四级闯关

> **A data-driven English learning SPA with spaced repetition, learning analytics, and gamification.**
> Built as a demonstration of product thinking, UX engineering, and learning algorithm design.

[![Deployed](https://img.shields.io/badge/deployed-GitHub%20Pages-brightgreen)](https://cx677.github.io)
[![Lines](https://img.shields.io/badge/code-5200%2B%20lines-blue)](index.html)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

---

## Why This Matters (for 东方国信 Interview)

This project demonstrates capabilities directly relevant to AI product development:

| Competency | Evidence |
|-----------|----------|
| **Product Thinking** | Complete learning product from UX design to algorithm to analytics — not just a tech demo |
| **Data-Driven Design** | Learning dashboard with radar charts, weekly trends, activity snapshots |
| **Algorithm Implementation** | Ebbinghaus spaced repetition (forgetting curve), adaptive quiz difficulty |
| **UX Engineering** | Dark/light theme system, keyboard shortcuts, onboarding wizard, responsive layout |
| **State Architecture** | Centralized state management with localStorage persistence |
| **User Psychology** | Streak tracking, achievement badges, combo system — designed for retention |

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

## For Interview: Key Talking Points

**1. "Why did you build this?"**
> "I wanted to understand what makes learning apps sticky. The spaced repetition algorithm, the streak system, the achievement badges — each feature is a hypothesis about user motivation. I built it to test those hypotheses, not just to write code."

**2. "What was the hardest part?"**
> "The Ebbinghaus algorithm. It's not just 'review after N days' — you need to handle partial mastery, adjust intervals based on performance, and maintain the review queue across sessions. The data model had to be both correct and space-efficient since everything lives in localStorage."

**3. "What would you do differently?"**
> "I'd add an AI-powered writing coach using an LLM API. The 'AI练笔' module is currently static — the next iteration would have real-time essay feedback. This is exactly the kind of 'AI+行业' application 东方国信 specializes in."

**4. "How does this relate to big data?"**
> "Every user interaction generates data — word difficulty, time spent, error patterns. The dashboard shows real-time analytics. At scale, this data could drive adaptive curriculum design, which requires the kind of data pipeline and analytics platform 东方国信 builds."

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
