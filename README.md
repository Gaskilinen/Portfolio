# Andrew Gaskell — Portfolio

The personal portfolio of **Andrew Gaskell**, UX Designer & Researcher at the Tote.

The site is a static, single-page-per-case-study build — hand-written HTML with embedded CSS, no build step, no JavaScript framework. It deploys to GitHub Pages directly from the repository root.

**Live site:** https://gaskilinen.github.io/Portfolio/

## What's in the site

- **Homepage** (`index.html`) — intro, featured case study (Lock In Your Price), selected work cards, current initiatives, approach, and closing.
- **Lock In Your Price** (`lock-in-your-price.html`) — current FY25–26 strategic project: introducing fixed-price betting alongside the pool.
- **Navigation** (`navigation.html`) — left-panel navigation redesign that drove a 6.48% lift in win conversion and 1.6M signposted events in 6 months.
- **Exotic Cross-Sell** (`exotic-cross-sell.html`) — racecard cross-sell component for exactas and trifectas, +8% lift in exacta bets.
- **Multiples** (`multiples.html`) — earlier work on the multiples experience.

Every case study follows the same numbered-section template — Context → North Star → Discovery → Design → Solution / Validation → Impact → Reflections → Next Steps — so they read consistently.

## Repository structure

```
.
├── index.html                       # Homepage
├── lock-in-your-price.html          # Case study
├── navigation.html                  # Case study
├── exotic-cross-sell.html           # Case study
├── multiples.html                   # Case study
├── images/                          # All case study and homepage images
├── navigating-winplace-clip.mp4     # Embedded video — Navigation case study
├── lock-in-your-price-validation.mp4 # Embedded video — LIYP validation
└── README.md
```

There is no `src/`, `dist/`, `node_modules/`, or build output — everything in the repo is what gets served.

## Running locally

Any static file server works. The simplest option:

```bash
# from the repo root
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser. (Opening the HTML files directly with `file://` mostly works too, but the relative paths and video embeds are happier over HTTP.)

If you have Node installed, `npx serve` is another one-liner.

## Deploying via GitHub Pages

The site is already configured to serve from the `main` branch root.

To enable Pages on a fresh repo:

1. Push the contents of this folder to `main`.
2. In the repository on GitHub, go to **Settings → Pages**.
3. Under **Source**, select **Deploy from a branch**.
4. Set **Branch** to `main` and **Folder** to `/ (root)`. Save.
5. Wait ~30–60 seconds. The site goes live at `https://<username>.github.io/<repo>/`.

Subsequent updates: just commit and push to `main` — Pages rebuilds automatically.

### Custom domain (optional)

To use a domain you own (e.g. `andrewgaskell.com`):

1. Add a `CNAME` file at the repo root containing just the domain name.
2. In your DNS provider, add an `A` record pointing to GitHub Pages' IPs (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153) or a `CNAME` record pointing to `<username>.github.io`.
3. In **Settings → Pages**, enter the custom domain and tick **Enforce HTTPS** once the certificate provisions (a few minutes).

## Editing the site

Each HTML file is self-contained. The `<style>` block at the top of every page holds all the CSS for that page, so to tweak a layout you only need to touch one file.

Shared design tokens used across pages:

| Token | Value | Use |
|---|---|---|
| `--dark` | `#302a3f` | Primary text, dark backgrounds, button borders |
| `--text` | `#57596b` (homepage) / `#4a4d5e` (case studies) | Body copy |
| `--surface` | `#f7f9fc` | Card backgrounds, insight cards |
| `--border` | `#c7c7d0` | Chip borders, dividers |
| `--divider` | `#d8d6e5` | Info-table rules |
| `--black` | `#090909` | Strongest text |

Typography is **Bebas Neue** (display) + **Lato** (body), loaded from Google Fonts.

To add a new case study, copy `navigation.html` as a template, swap the content, and add a new card in `index.html` with the matching `href`.

## Credits

- Design system, content, and copy: Andrew Gaskell
- Site build: Andrew Gaskell with Claude Cowork
- Fonts: [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue) and [Lato](https://fonts.google.com/specimen/Lato) via Google Fonts

## Contact

- Email: [andygaskell10@outlook.com](mailto:andygaskell10@outlook.com)
- LinkedIn: [Andrew Gaskell](https://www.linkedin.com/in/andrew-gaskell-4092a5191)
