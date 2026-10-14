# IslandOS — iPhone 11 PWA

A starter productivity PWA with:
- Dynamic Island-inspired pill **inside the app**
- Task list saved in browser local storage
- Focus timer and 5-minute timer preset
- Accent color cycling
- Installable PWA manifest and basic offline cache

## Publish using GitHub Pages from an iPhone

1. Open Safari and go to https://github.com/new
2. Sign in, create a repository named `islandos`, and set it to **Public**.
3. Create/upload these four files to the repository root: `index.html`, `manifest.json`, `sw.js`, `icon.svg`. You can also upload `README.md`.
4. On the repository page, open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select branch `main`, folder `/(root)`, then tap **Save**.
7. Wait for GitHub Pages to publish. The site URL will look like `https://YOUR-USERNAME.github.io/islandos/`.
8. Open the published URL in **Safari** on the iPhone.
9. Tap **Share → Add to Home Screen**. If shown, enable **Open as Web App**, then tap **Add**.

## Important iOS limitations

- The pill only appears inside IslandOS. A website/PWA cannot float over other apps or replace Apple's system Dynamic Island.
- The timer works while the app is running in the foreground, but iOS may suspend browser timers in the background.
- This starter does not include server-backed push notifications or Supabase sync.
- Tasks are stored locally in the browser on this device. Clearing Safari website data can remove them.
- For a future Supabase version, use Row Level Security and never place a service-role key in client-side code.

## Updating

Edit `index.html` in GitHub and commit the changes. Reload the published site. If old content is cached, close/reopen the PWA or clear the site's website data.


## Apple Shortcuts actions (after updating/redeploying)
Replace `YOUR-USERNAME` with your GitHub username. Create a shortcut with the **Open URLs** action for any of these:

- Open dashboard: `https://YOUR-USERNAME.github.io/islandos/`
- Open task entry: `https://YOUR-USERNAME.github.io/islandos/?action=tasks`
- Add a task prompt: `https://YOUR-USERNAME.github.io/islandos/?action=add-task`
- Start focus timer: `https://YOUR-USERNAME.github.io/islandos/?action=focus`

The focus action starts the timer when the page loads. iOS may open the website in Safari rather than in standalone app mode depending on how the shortcut is launched. These URLs do not create a system-wide Dynamic Island overlay.
