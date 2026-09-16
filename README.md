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
Connected to Vercel for automatic production deployments.
