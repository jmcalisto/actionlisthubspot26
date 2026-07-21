# Action List HubSpot Walkthrough

An interactive training simulator that walks Wall Street English consultants through the
HubSpot standard operating procedure (SOP) for working the daily **Action List** — from
logging in and bookmarking Tasks to closing the loop with a pinned note on the contact record.

## Purpose

This is a hands-on, click-through trainer. Instead of reading the SOP, staff practise the
exact workflow in a safe, simulated "HubSpot Sandbox" environment. Each step must be
completed correctly before the next one unlocks, so trainees finish having performed every
action in order.

## How to use

1. Open `index.html` directly in any modern web browser — double-click the file or drag it
   into a browser tab.
2. No installation, server, or build step is required.
3. Work through the five steps in order. Each step gates the next, and a progress bar and
   task checklist track how far you've got.

## The five steps

1. **Log in & bookmark Tasks** — Sign in to HubSpot, find Tasks from the CRM menu, and
   bookmark the page since it's used every day.
2. **Select a view & edit columns** — Choose a task view, add the Priority column, move it
   next to Task → Contacts, and sort by priority.
3. **View & complete a task** — Open a task, read the notes, check the Services Agreement to
   confirm level/unit/lesson, decide how to contact the student, then mark the task complete.
4. **Create & pin a note** — Update the record with what happened, add a note, and pin it so
   the whole team can see it.
5. **Complete** — Success screen with a completion code (`WSE-AL-TASK-COMPLETE-2026`) to copy
   into the Knowledge Check.

## Tech & structure

- **Single-file app:** everything lives in `index.html`.
- **Vanilla stack:** plain HTML, CSS, and JavaScript — no frameworks, libraries, or build
  tools. The only external resource is the Lexend Google Font.
- **Inside the file:** inline `<style>` (CSS, theming, animations) near the top, the five
  step panels (`panel-0` … `panel-4`) plus modals in the HTML body, and inline `<script>`
  blocks (i18n, navigation, validation, progress tracking) near the bottom.
- **Client-side only:** there is no backend and no API calls. All progress is held in memory,
  so refreshing the page resets the walkthrough.
- **Desktop-oriented:** the layout assumes a wide screen and is not designed for mobile.

## Notes

- All content is demo/instructional data (for example, the sample student "Maria Novak"); it
  is not connected to a live HubSpot instance.
- Progress is not saved between sessions — closing or refreshing the page starts over.
