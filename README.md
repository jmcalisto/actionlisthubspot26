# Action List HubSpot Walkthrough

An interactive training simulator that walks Wall Street English consultants through the
HubSpot standard operating procedure (SOP) for working the daily **Action List** — from
logging in and bookmarking Tasks to closing the loop with a pinned note on the contact record.

## Purpose

This is a hands-on, click-through trainer. Instead of reading the SOP, staff practise the
exact workflow in a safe, simulated "HubSpot Sandbox" environment. A coach panel with a
bouncing arrow points at exactly what to click next, so trainees are never stuck guessing
what the current step wants from them.

## How to use

1. Open `index.html` directly in any modern web browser — double-click the file or drag it
   into a browser tab.
2. No installation, server, or build step is required.
3. Work through the four modules in order. The coach panel tells you what to do at each step,
   a floating arrow points at the exact element to click, and a progress strip along the top
   tracks how far you've got.
4. Progress is saved automatically (to the browser's local storage), so closing the tab and
   reopening the file later offers to resume where you left off.

## The four modules

1. **Log in & add a bookmark** — Sign in to HubSpot, find Tasks from the CRM menu, and
   bookmark the page since it's used every day.
2. **Select a view & edit columns** — Choose a task view, add the Priority column, and sort
   by priority.
3. **View & complete a task** — Open a task, check the Services Agreement to confirm
   level/unit/lesson, decide how to contact the student, then mark the task complete.
4. **Create & pin a note** — Update the record with what happened, add a note, and either pin
   it or wrap up via the alternate note-only branch — then land on a completion screen with a
   code (`ACTION-LIST-2026`) to copy into the Knowledge Check.

## Tech & structure

- **Single-file app:** everything — markup, styles, and logic — lives in `index.html`.
- **Vanilla stack:** plain HTML, CSS, and JavaScript. No frameworks, libraries, build tools,
  or external fonts/assets — the system font stack is used throughout, so the file works
  fully offline.
- **Step-engine architecture:** a `STEPS` array describes every screen (`key`, `module`,
  `title`, `body`, a `render()` that builds that step's fake-HubSpot UI, and a `wire()` that
  attaches the click handling that advances the walkthrough). A small engine
  (`renderStep()` / `advance()`) drives the trainee through them, including a branching path
  in module 4 (`branch: 'complete'` vs `'note'`) so either valid real-world outcome is
  accepted.
- **Progress persistence:** current step and completed branches are saved to
  `localStorage` (`wse_hubspot_tasklist_progress_v1`) after every step, with a resume banner
  offered on reload and a restart option.
- **Accessibility:** keyboard navigation and ARIA labelling are wired into the interactive
  hotspots via `enhanceHotspotA11y()`.
- **Client-side only:** there is no backend and no API calls.
- **Desktop-oriented:** the layout assumes a wide screen and is not designed for mobile.

## Notes

- All content is demo/instructional data (for example, the sample student "Abdelilah
  Karimi"); it is not connected to a live HubSpot instance.
- This version does not include the multi-language switcher used in earlier iterations of
  this trainer — it is English-only.
