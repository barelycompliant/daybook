# Daybook

A project by [Barely ⊅ Compliant Studios](https://barelycompliant.dev).

**Production URL:** https://daybook.barelycompliant.dev/  
Technically within specifications.

## Deployment

Upload `index.html`, `styles.css`, `app.js` and `favicon.svg` to the root of any static web host. No build, backend, package installation, API keys or environment variables are required. For Cloudflare Pages, use direct upload and connect the custom domain in the Pages dashboard. Alternatively, open index.html locally; browser storage behavior for file URLs varies. For local development run `python -m http.server 8000` in this directory and open http://localhost:8000.

## Features and workflow

1. **School & periods:** configure school and optional student name, custom rotation labels, rotating or fixed weekday mode, weekday mapping and named bell periods. Save settings and bell times separately. Copy school data from another JSON while retaining classes matched by period label and rotation label.
2. **Classes:** add names, teachers, rooms, notes and colors. Use the meeting matrix, row/column bulk selection or shorthand such as `1AD, 2BCF` or `56BE` for numeric periods and single-character day labels. Confirm reassignment when a slot is already occupied.
3. **Weekly grid:** inspect the color-coded schedule and click a slot to assign, clear or create a class.
4. **Calendar:** set inclusive date range, starting rotation label and meeting weekdays. Mark holiday ranges, force individual day labels, restore automatic rotation, or edit notes in the full-year list. Forced labels re-anchor subsequent rotating days. Holidays do not advance rotation. Fixed weekday mode uses the configured weekday mapping.
5. **Export:** select a date range, IANA timezone or floating times, title template, room prefix, free-period inclusion/name/location, teacher and notes, merging and optional reminders. Preview events and download ICS or CSV. Title tokens: `{class}`, `{day}`, `{period}`, `{teacher}`, `{room}`, `{school}`. CSV contains local wall-clock times and does not carry timezone or alarm metadata.
6. **Working files:** Export JSON downloads a complete workspace snapshot; Open JSON imports it after confirmation. Both original formats are supported, including legacy Letter Day Schedule JSON. No file handle is retained and no external file is automatically updated. Legacy explicit calendars are converted into date overrides; unassigned dates become off days. School-only import retains matching class meetings and warns about unmatched meetings.

## Storage and privacy

Saved changes are automatically retained in localStorage on the current browser/origin. No cookies, tracking, external libraries, network APIs, account or server storage. Use JSON backups for portability and recovery. Browser storage can be cleared or unavailable. JSON files are plain text and may contain personal information. Complete edits with the relevant Save/Apply button before exporting. Reset workspace is under How it works.

## Calendar behavior and limitations

One bell schedule and class roster apply to the entire export range. For schedule changes midyear, keep separate JSON snapshots and export separate ranges. ICS is a static import, not a live subscription; use a dedicated calendar and replace old imports to avoid duplicates. Merging consecutive periods can include passing time. Timezone conversion uses the browser's Intl timezone database; nonexistent clock-change times are rejected. Calendar ranges are limited to ten years. No automatic holiday lookup. Legacy files containing invalid or conflicting assignments may be rejected. Browser dialogs are used for confirmation and quick grid assignment.

## Files

- `index.html` — semantic page layout, controls and dialogs
- `styles.css` — compact responsive layout and brand palette
- `app.js` — workspace, scheduling, migration, storage and export logic
- `favicon.svg` — studio symbol
- `README.md` — this guide

## Brand

Evergreen `#001f11`, Gunmetal `#3b3b3b`, Jet Black `#22333b`, Alice Blue `#e6edf3`, Deep Space Blue `#2d374b`, Deep Navy `#001544`. Class colors are user-selectable; secondary contrast and warning colors support usability.

© 2026 Barely Compliant Studios.
