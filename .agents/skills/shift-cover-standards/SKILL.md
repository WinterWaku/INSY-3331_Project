---
name: shift-cover-standards
description: Design, UX, quality, and data rules for building and extending the ShiftCover peer-coverage web app. Use in every build iteration across all team members' laptops to maintain consistency, mobile responsiveness, and end-to-end functionality.
---

# ShiftCover Product & Quality Standards

## 1. Core Purpose & Scope
ShiftCover is a lightweight, zero-install mobile web log that enables independent local coffee shop and retail supervisors to post open shifts and let staff members claim coverage instantly, eliminating 6:00 AM group-text anxiety.

## 2. Technical & Architecture Rules
- **Single-File Structure**: Everything must be self-contained in `index.html` (HTML, CSS, and JavaScript) to enable instant deployment via GitHub Pages.
- **Zero-Dependency / No External Builds**: Use standard vanilla JavaScript, Tailwind CSS (via CDN), or clean CSS. No backend servers, no build tools, and no API keys required.
- **End-to-End Working Functionality**: No dead buttons or hard-coded placeholders. Users must be able to add a shift, view the live roster, and claim/update shift statuses dynamically with local state persistence (e.g., `localStorage`).

## 3. UI/UX & Mobile Responsiveness
- **Mobile-First Design**: Optimized for quick interactions on a smartphone screen during high-stress morning hours.
- **High-Contrast Status Indicators**: Must use clear, color-coded visual badges for shift states:
  - `Red`: Urgent / Uncovered (< 12 hours)
  - `Yellow`: Open / Pending Coverage
  - `Green`: Covered / Approved
- **Friendly Error Handling**: Clear, reassuring validation messages if required fields are missing (e.g., "Please select a shift time before posting").

## 4. Privacy & Data Rules
- **No Medical/Confidential Over-collection**: Never capture, store, or display sensitive personal health details or confidential medical reasons for dropping shifts. Use standardized dropdown reasons instead (e.g., "Personal Emergency", "Schedule Conflict", "Unwell").
- **Minimal Data Overhead**: Require only essential fields: Employee Name, Role, Shift Date, Start/End Time, and Status.

## Extended Iteration Rules

### State & Persistence
- All shift postings, claims, and availability toggles must immediately persist to `localStorage`.
- Include a "Reset Demo Data" button in the footer for easy live user testing.

### Accessibility & Speed
- Primary action buttons (Post, Claim, Approve) must be minimum 48px touch targets for easy tapping on mobile.
- Form inputs must default to sensible values (e.g., today's date for shift requests).
