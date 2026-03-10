# FamilyConnect

**Train Together, Grow Together**

A Progressive Web App (PWA) providing personalized weekly training timetables for Siva and Sutharia, covering yoga, breathing exercises, and gym/calisthenics workouts.

## Features

- **Personalized schedules** for Siva and Sutharia with condition-aware modifications
- **7-day training plan** with daily yoga, breathing (pranayama), and exercise routines
- **Activity type filters** — view All, Yoga, Breathing, or Exercise
- **Auto-selects today** — opens to the current day's schedule
- **Pain scale guidance** — Go (0-2), Modify (3-4), Stop (5+)
- **Installable PWA** — works from iPhone/Android home screen
- **Offline support** — full functionality without internet via Service Worker

## Training Schedule Overview

| Day | Type | Focus |
|-----|------|-------|
| Monday | REST | Yoga + Breathing + Active Recovery |
| Tuesday | GYM A | Hinge + Push/Pull + Arms + Core |
| Wednesday | CALISTHENICS A | Full Body + Pull-ups + Arms |
| Thursday | REST | Mobility + Recovery |
| Friday | GYM B | Posterior + Vertical Pull + Shoulders |
| Saturday | CALISTHENICS B | Squat + Posterior + Pull-ups |
| Sunday | GYM C | Upper Back + Squat + Carry |

## Tech Stack

- **HTML5 + CSS3 + Vanilla JavaScript** — single-file SPA, no frameworks
- **Service Worker** — cache-first offline strategy
- **PWA Manifest** — installable on iOS and Android
- **Google Fonts** — Inter typeface

## File Structure

```
/index.html          — Main app (all HTML, CSS, JS, and data)
/manifest.json       — PWA manifest
/sw.js               — Service Worker
/icons/icon-192.svg  — App icon 192px
/icons/icon-512.svg  — App icon 512px
/docs/               — Design specs and future plans
```

## Deployment

Hosted on **GitHub Pages** at: https://sivaprasad.github.io/FamilyConnect/

The app is a static site — just push to `main` and GitHub Pages serves it.

## Theme

- Background: Soft warm white (#FFF8F5)
- Primary: Coral (#E8634A)
- Yoga cards: Lavender (#F3EEFF)
- Breathing cards: Sage green (#EEFBF5)
- Exercise cards: Warm amber (#FFF5E6)

## Built by

**4S Nexus** — Built with love
