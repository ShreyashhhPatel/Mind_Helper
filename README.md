# MindFlow (Mind Helper)

Single-file mental wellness web app that runs fully in the browser.

## 1) What this app does
- Shows a 16-question self-assessment (scale 1 to 5).
- Calculates a total score out of 80.
- Maps score to one of 3 modes:
  - `Relaxation Mode` (16-35)
  - `Venting Mode` (36-55)
  - `Direction Mode` (56-80)
- Opens a guided screen based on the selected mode.

## 2) Core user flow
- Landing screen -> Start Assessment
- Question screens -> Next/Back navigation
- Loading screen -> Result screen
- Result screen -> Enter selected mode
- Mode completion -> Back to home

## 3) Scoring logic
- Total score = sum of all 16 answers.
- Each answer range: 1 to 5.
- Minimum total: 16, maximum total: 80.
- Mode selection:
  - `<= 35` -> Relaxation
  - `<= 55` -> Venting
  - `> 55` -> Direction

## 4) Tech stack
- Plain HTML, CSS, and JavaScript
- No backend
- No database
- No build step required

## 5) Project structure
- `mindflow.html` -> Main app (UI, styles, logic)
- `index.html` -> Root redirect to `mindflow.html`
- `vercel.json` -> Vercel rewrite for `/` -> `/mindflow.html`

## 6) Run locally
Open `mindflow.html` directly in browser, or run a local static server:

```bash
cd ../Mind_Helper
python3 -m http.server 8000
```

Then visit: `http://localhost:8000`

## 7) Deploy (Vercel)
- Import this repository in Vercel.
- Framework preset: `Other` (static site).
- Keep root directory as project root.
- Deploy.

Why this works:
- `index.html` handles root requests.
- `vercel.json` rewrites `/` to `mindflow.html` to avoid 404/NOT_FOUND.

## 8) Privacy behavior
- User responses are kept in runtime memory only.
- No API calls and no persistent storage by default.

## 9) Quick customization points
- Edit questions in `questions` array in `mindflow.html`.
- Edit score thresholds in `showResult()`.
- Edit affirmations inside `renderRelax()`.
- Edit mode text/content inside `renderVent()` and `renderDirection()`.

## 10) Future improvements (optional)
- Save session to `localStorage`.
- Add dark/light theme toggle.
- Export vent/direction notes to text file.
- Add accessibility pass (keyboard + ARIA labels).
