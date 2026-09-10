# singadev-contacts

Static contact page for [SingaDev](https://www.meetup.com/singadev/), Singapore's developer meetup community. Links to Meetup, email, LinkedIn, and Telegram, with a terminal-inspired light/dark theme.

## Structure

- `index.html` — page markup
- `styles.css` — theme tokens + layout (dark is default, light via the toggle or `prefers-color-scheme`)
- `script.js` — theme toggle logic (persists choice in `localStorage`)
- `favicon.svg` — simple terminal-style placeholder favicon (the real logo isn't legible at 16px, so this stays a text mark)
- `assets/logo.png` — SingaDev logo, trimmed/optimized from `assets/logo-source.png` (the original file provided)
- `assets/logo-source.png` — original, untouched logo artwork, kept for future re-exports

## Customizing branding

- The real logo is already wired up (`.wordmark img` in `index.html`, sourced from `assets/logo.png`). To update it, replace `assets/logo-source.png` and re-export a trimmed/resized `assets/logo.png` (e.g. via `magick logo-source.png -trim +repage -resize 900x assets/logo.png`).
- The `--accent` color in `styles.css` (`:root`) drives the cursor blink, link icons, and toggle highlight — currently a terminal green that complements the logo's frog mascot.

## Local preview

Open `index.html` directly in a browser, or serve the folder locally:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch".
4. Choose the `main` branch and `/ (root)` folder, then save.
5. GitHub will publish the page at `https://<username>.github.io/<repo>/`.
