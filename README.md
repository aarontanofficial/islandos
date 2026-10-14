# IslandOS 2.0 — iPhone 11 PWA

## Features
- Minimal glass-like responsive design
- Tasks and checklist
- Focus timer (25 minutes) and 5-minute break timer
- Quick notes
- Daily schedule entries
- Goals, active-day streak and weekly active-day summary
- URL actions for Apple Shortcuts
- Basic service-worker offline cache

## Update existing GitHub Pages site from iPhone
1. Download and extract `IslandOS-2.0-iPhone-PWA.zip` in the iPhone Files app.
2. Open https://github.com/aarontanofficial/islandos
3. Replace the existing root files `index.html`, `manifest.json`, `sw.js`, and `icon.svg` with the files in this folder. Do not upload the whole folder as a subfolder.
4. Commit changes to the branch/folder your Pages site publishes from (commonly `main` and `/(root)`). GitHub documents this under Settings → Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
5. Wait for deployment, then open https://aarontanofficial.github.io/islandos/ in Safari and refresh. If old UI persists, close the installed PWA and reopen it; you may need to clear the site's website data.
6. If the PWA looks old, service-worker cache may take a refresh/reopen to update.

## Apple Shortcuts
Create each shortcut using Shortcuts → + → Add Action → Open URLs. Use these URLs:
- Dashboard: https://aarontanofficial.github.io/islandos/
- Tasks: https://aarontanofficial.github.io/islandos/?action=add-task
- Focus: https://aarontanofficial.github.io/islandos/?action=focus
- Quick note: https://aarontanofficial.github.io/islandos/?action=add-note
- My Day: https://aarontanofficial.github.io/islandos/?action=my-day
- Add goal: https://aarontanofficial.github.io/islandos/?action=goal

Depending on iOS, Open URLs may open Safari instead of the standalone PWA. For a shortcut icon: shortcut details → Add to Home Screen, where available.

## Data and limitations
- Data is stored in localStorage in the browser/app context. Browser storage is not a backup and can be cleared by iOS.
- This version does not sync between devices and does not provide system calendar integration, alarms that are guaranteed while the app is closed, or push notifications.
- The timer may pause or be suspended when iOS backgrounds the PWA. Use Apple's Clock/Reminders for dependable system-level alarms.
- iPhone 11 has a notch, not Apple's Dynamic Island. A PWA cannot display a persistent floating overlay over other apps, register native Home Screen widgets, or control other apps' music playback.
- All site files are public. Never put private secrets or API keys in this repository.
