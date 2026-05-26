# vigil-site

Marketing landing page + privacy policy + support page for [Vigil](https://github.com/juergen-kc/Vigil) — a spatial situation room for Mac and Apple Vision Pro.

Published at <https://juergen-kc.github.io/vigil-site/>.

## Structure

```
index.html         — Landing page
privacy/index.html — Privacy policy
support/index.html — Support & FAQ
assets/
  styles.css       — Shared stylesheet (DAY/NIGHT theme via prefers-color-scheme)
  favicon.svg      — SVG favicon that adapts to color scheme
.nojekyll          — Disables Jekyll processing on GitHub Pages
```

No build step. No framework. No JavaScript. Push to `main`, GitHub Pages serves the files as-is.

## Design

Visually mirrors [hush-site](https://github.com/juergen-kc/hush-site) for consistency across the apps. Color palette is derived from the Vigil app icon:

- **DAY** (light theme, default): warm paper-cream background, ink-dark text, amber accent
- **NIGHT** (dark theme, auto via `prefers-color-scheme: dark`): midnight navy background, cyan-teal text (owl-glow), amber accent

Typography is system monospace — `ui-monospace`, falling back to SF Mono / JetBrains Mono / Menlo — chosen to match the calm, instrument-panel feel of the app itself.

## Editing

Open any of the HTML files and edit. Test locally:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

Note that internal links are absolute (`/vigil-site/...`) so they only resolve correctly under the GitHub Pages path. For local preview, the simplest fix is to symlink the repo into a `vigil-site` directory:

```bash
mkdir -p /tmp/preview && ln -s "$(pwd)" /tmp/preview/vigil-site && cd /tmp/preview && python3 -m http.server 8000
# then open http://localhost:8000/vigil-site/
```

## License

The site content (HTML/CSS/copy) is © Juergen Klaassen and not separately licensed for reuse. The Vigil app itself is source-available — see the [main repo](https://github.com/juergen-kc/Vigil) for terms.
