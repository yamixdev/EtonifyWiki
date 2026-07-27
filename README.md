# Etonify Documentation

Static RU/EN documentation for [Etonify](https://github.com/yamixdev/Etonify).

## Architecture

- No framework, package manager, build step, analytics, or JavaScript runtime dependencies.
- Typography and interface symbols use Google Fonts with system-font fallbacks.
- `index.html` contains the application shell.
- `assets/content.js` contains both language versions and is loaded once.
- `assets/app.js` handles navigation, search, theme, and language preferences.
- `assets/styles.css` contains responsive light/dark presentation and print styles.
- A scheduled GitHub Actions workflow refreshes `assets/latest-release.json` from GitHub Releases; visitors only load the local snapshot.
- Navigation uses URL hashes, so switching sections never loads another page.

## Local preview

The site also works when `index.html` is opened directly. For an HTTP preview:

```powershell
python -m http.server 4173
```

Then open `http://localhost:4173`.

## GitHub Pages

After committing the files, open repository settings and select:

`Settings → Pages → Deploy from a branch → main / (root)`

The `.nojekyll` marker keeps GitHub Pages from applying Jekyll processing.
