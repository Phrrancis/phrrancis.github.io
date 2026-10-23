# francis.github.io

Source for my personal website and blog, live at
[phrrancis.github.io/francis.github.io](https://phrrancis.github.io/francis.github.io/).

It is a plain static site: hand-written HTML and CSS, a small script for dark
mode, and no build step. Pushes to `main` are deployed by GitHub Actions
(`.github/workflows/static.yml`).

## What's on the site

- **Home**: short bio, side projects, recent writing, and contact links.
- **Blog**: posts on payments, data science, product management, and economics.
- **RSS**: `feed.xml`, hand-maintained.
- **Dark mode**: follows the system preference, with a manual toggle.

## Layout

```
.
├── .github/workflows/static.yml   # Deploys the repo to GitHub Pages on push to main
├── index.html                     # Home page
├── blog/
│   ├── index.html                 # Post list, newest first
│   ├── _template.html             # Starting point for a new post
│   └── YYYY/                      # One folder per year; images live in YYYY/images/
├── feed.xml                       # RSS feed
├── stylesheets/                   # normalise.css and stylesheet.css
├── js/theme.js                    # Dark mode toggle
├── favicon.svg
└── profile_pic.jpg
```

## Working locally

There is nothing to install. Open `index.html` in a browser, or serve the
folder so relative links behave the same as on GitHub Pages:

```
python3 -m http.server 8000
```

Then visit <http://localhost:8000/>.

The site is published under the `/francis.github.io/` subpath, so links and
asset paths are relative rather than rooted at `/`.

## Adding a blog post

1. Copy `blog/_template.html` to `blog/YYYY/your-slug.html` and replace the
   `POST_TITLE`, `POST_SUMMARY`, `POST_SLUG`, and `YYYY-MM-DD` placeholders.
2. Add the post to the top of the list in `blog/index.html`.
3. Add it to the "Writing" list in `index.html`, keeping only the three newest.
4. Add an `<item>` at the top of `feed.xml` and update `lastBuildDate`.

## Third-party services

- Google Fonts (Roboto Mono)
- [Plausible](https://plausible.io) for privacy-friendly analytics
