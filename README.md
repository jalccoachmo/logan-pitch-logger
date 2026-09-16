# Logan Road Pitch Logger — PWA

This folder is ready to deploy as a static website/PWA.

## Vercel
1. Create a new Vercel project and upload/deploy this folder (or push it to a GitHub repo connected to Vercel).
2. No build command or framework is required. The root file is `index.html`.
3. Open the HTTPS Vercel URL in Safari on the iPad.
4. Tap **Share → Add to Home Screen → Add**.
5. Launch **Logan Logger** from the iPad home screen.
6. Open it once while online after each new deployment so the newest app shell is cached. After that, the logger works offline.

## Important
- Do not test PWA installation by opening `index.html` directly from Files (`file://`). Service workers require HTTPS (or localhost).
- Rosters, lineups, and game data are stored locally on that device/browser.
- Export the Synergy CSV and/or Backup JSON at the end of the game.
- The included roster CSV contains only: Number, Name, Bats, Throws, Position.


## v4.5 game-flow update
- Ball 4 records `PAResult=Walk`, resets the count, and advances to the next batter automatically.
- Strike 3 on a called or swinging strike records `PAResult=Strikeout`, adds an out, resets the count, and advances automatically. If it is the third out, the half-inning ends automatically.
- Undo restores the pre-pitch count, outs, batter, and lineup position.

## v4.6 in-play update
- Choosing **In Play** now opens a Play Result panel.
- Results: Out, Double Play, 1B, 2B, 3B, HR, Error, Fielder's Choice, Sac Fly, Sac Bunt.
- Out adds 1 out; Double Play adds 2; Sac Fly/Sac Bunt add 1.
- Fielder's Choice asks whether 0, 1, or 2 outs were recorded.
- Every in-play result completes the plate appearance and advances to the next batter.
- If the play creates the third out, the half-inning ends automatically.
- CSV exports include PlayResult and OutsOnPlay.


## V4.9 event timestamps
Every saved pitch is automatically stamped at the moment it is logged. Both CSV exports include `TimestampUTC`, `EventTimestamp`, and `LocalTime` for Synergy event-sync workflows. No video clock or manual sync-start step is required.


## V4.9 — Runs Scored
- Added Runs Scored (0–4) to every pitch/event.
- Home Run and Sac Fly default to 1 run; tagger can change to 0–4.
- Added automatic Logan and Opponent run totals to the scoreboard.
- Added RunsScored, LoganScoreAfter, and OpponentScoreAfter to both CSV exports.
- Runs are tied to the batting team and automatically reverse when the last pitch is undone.
