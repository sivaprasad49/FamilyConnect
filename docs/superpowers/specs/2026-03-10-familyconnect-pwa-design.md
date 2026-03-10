# FamilyConnect PWA — Design Spec

## Overview
Convert existing training timetable HTML into an installable Progressive Web App called "FamilyConnect" for Siva and Sutharia. Targets iPhone 17 and Samsung 24 Ultra.

## Branding
- **App name:** FamilyConnect
- **Tagline:** "Train Together, Grow Together"
- **Company:** 4S Nexus
- **Footer:** "Built with love by 4S Nexus"
- **Icon:** Heart with connected-people silhouette, coral/warm tones

## Theme — Warm & Energetic
- **Background:** Soft warm white (#FFF8F5)
- **Primary:** Coral (#E8634A)
- **Yoga cards:** Soft lavender (#F3EEFF / #7C5CBF border)
- **Breathing cards:** Soft sage green (#EEFBF5 / #3D9970 border)
- **Exercise cards:** Warm amber (#FFF5E6 / #C4841D border)
- **Text:** Dark charcoal (#2D2D2D)
- **Secondary text:** (#6B7280)
- **Font:** Inter (Google Fonts)
- **Style:** Rounded corners, soft shadows, warm gradients

## PWA Requirements
- Installable on home screen (iOS + Android)
- Full-screen standalone display
- Offline via Service Worker (cache-first)
- App manifest with name, icons, theme color
- Splash screen support
- Icons: 192px + 512px

## Functionality
- Person toggle (Siva / Sutharia)
- Day filter (Mon-Sun, auto-selects today)
- Type filter (All / Yoga / Breathing / Exercise)
- All existing training data preserved exactly
- Pain scale guide in footer

## File Structure
```
/index.html          — Main app
/manifest.json       — PWA manifest
/sw.js               — Service Worker
/icons/icon-192.svg  — App icon 192px
/icons/icon-512.svg  — App icon 512px
```
