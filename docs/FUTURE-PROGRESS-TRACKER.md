# Future Feature: Progress Tracker

## Status: Planned (not yet implemented)

## Overview

Add a progress tracking system to FamilyConnect where Siva and Sutharia can mark individual exercises as completed after each session, view weekly reports, and compare progress side-by-side. The feature should motivate consistent training over a 3-month period.

## Requirements

### Core Tracking
- **Individual exercise completion** — each exercise/yoga pose/breathing technique can be marked as done
- **Partial completion support** — e.g., 18/25 exercises done for the day counts as partial progress
- **One-tap "completed" button** per exercise item after finishing
- **Daily completion summary** — shows X/Y items completed per activity type

### Weekly Report
- Visual weekly report showing completion rates
- Breakdown by activity type (Yoga, Breathing, Exercise)
- Week-over-week trend (improving, maintaining, declining)

### 3-Month Motivation Focus
- Designed to motivate consistent training over 3 months (~90 days)
- Streak tracking (consecutive days with activity)
- Motivational elements (progress bars, milestones, encouragement)

### Siva vs Sutharia Comparison
- Side-by-side weekly comparison view
- Completion percentage per person per activity type
- Friendly competition/accountability element

## Technical Decisions Made

### Backend: Firebase (Free Tier)
- **Firebase Auth** — Google Sign-In for both users
- **Firebase Firestore** — real-time database for progress data
- **Why Firebase**: Free tier is more than sufficient (2 users, ~100 reads/writes per day vs 50,000/20,000 daily limits), real-time sync so both users see each other's progress, no server to maintain
- **No credit card required**

### Deployment: No Change
- Frontend stays on **GitHub Pages** as a static PWA
- Firebase SDK loaded via CDN in `index.html`
- Architecture: `GitHub Pages (PWA) → Firebase Auth → Firestore`

### Data Storage Design (Proposed)
```
Firestore structure:
  /users/{userId}
    - name: "Siva" | "Sutharia"
    - email: string

  /progress/{date}_{userId}
    - date: "2026-03-10"
    - userId: string
    - name: "Siva" | "Sutharia"
    - completions: {
        yoga: ["Tadasana", "Surya Namaskar A×3", ...],
        breathing: ["Ujjayi 4-7-8 ×4", ...],
        exercise: ["Barbell RDL 3×8", ...]
      }
    - totalItems: 25
    - completedItems: 18
    - timestamp: server timestamp
```

## Firebase Setup Steps

1. Go to console.firebase.google.com
2. Create project named "FamilyConnect" (disable Analytics)
3. Enable Authentication → Google provider
4. Create Firestore Database → asia-south1 region → test mode
5. Register Web App → get firebaseConfig object
6. Add Firebase SDK + config to index.html
7. Add Firestore security rules (restrict to authenticated users)

## Privacy Note

Personal details (age, weight, height, medical conditions) have been removed from the public-facing app. These details are kept only in the private training timetable source documents in `docs/`. Do NOT add personal/medical info back to `index.html` or any public-facing file.

## UI Design Notes

- Add a small checkbox/circle next to each exercise item
- Tap to mark as done (fills in, maybe with a satisfying animation)
- Add a "Progress" tab/view alongside the current timetable
- Weekly report could be a simple bar chart or progress rings
- Comparison view: two columns, one per person
- Keep the existing warm coral/lavender/green color theme
- Mobile-first, touch-friendly tap targets

## Implementation Priority

1. Firebase setup + auth (Google Sign-In)
2. Individual exercise completion tracking (checkboxes)
3. Daily completion summary
4. Weekly report view
5. Siva vs Sutharia comparison view
6. Streak tracking + motivational elements
7. 3-month milestone celebrations
