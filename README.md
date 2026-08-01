# hvotm.github.io

Personal portfolio site for Hung (Dylan) Vo, redesigned after the minimal,
typography-first style of [di.nmfay.com/about](https://di.nmfay.com/about).

Live at: **https://hvotm.github.io**

## Design reference — what the inspiration site uses

An analysis of `di.nmfay.com/about`, which this site follows:

| Aspect | Reference site | This site |
|---|---|---|
| Layout | Single centered column, 800px wide, 40px side padding | Same, but `max-width` so it's responsive |
| Header | Flexbox: name (h1) left, inline lowercase nav links right | Same |
| Body font | [Work Sans](https://fonts.google.com/specimen/Work+Sans) 300 (light), justified paragraphs | Same, line-height bumped 1.25 → 1.5 |
| Heading font | [Wire One](https://fonts.google.com/specimen/Wire+One) (tall condensed), `text-transform: lowercase` | Same |
| Monospace | Inconsolata for `code`/`pre` | Same (Google Fonts instead of self-hosted) |
| Type scale | h1 3em · h2 2.5em · h3 2em | Same |
| Colors | Ink `#15151e` on white, links `#2e1eaa` (indigo), no underline until hover | Same |
| JavaScript | One tiny script | None — pure HTML/CSS |
| Mobile | Fixed width (overflows on phones) | Media query stacks the header below 600px |

## Tech stack

Deliberately minimal — no framework, no build step, no `node_modules`:

- **HTML5** — one page ([index.html](index.html)) with semantic tags (`header`, `main`, `article`, `footer`, `abbr`)
- **CSS3** — one stylesheet ([css/site.css](css/site.css)) using flexbox, custom properties, and a single media query
- **Google Fonts** — Work Sans, Wire One, Inconsolata (loaded via `<link>`, nothing to install)
- **GitHub Pages** — free hosting; pushing to `main` deploys automatically

A framework (React/Vue/Svelte/Next) is unnecessary for a static one-page portfolio —
it would add a build pipeline and dependencies for zero benefit here. If the site
later grows a blog, the natural upgrade path is a static site generator
([Eleventy](https://www.11ty.dev/), [Astro](https://astro.build/), or
[Hugo](https://gohugo.io/)) rather than an SPA framework.

## Run locally

No build step, so any static file server works:

```sh
# Python (preinstalled on most systems)
python -m http.server 8000
# then open http://localhost:8000
```

Or in VS Code: install the **Live Server** extension and click "Go Live".
(Opening `index.html` directly in a browser also works.)

## Deploy

This repo is named `hvotm.github.io`, so GitHub Pages serves it from the `main`
branch root automatically:

```sh
git add -A
git commit -m "your message"
git push
```

Changes appear at https://hvotm.github.io within a minute or two.

- `_config.yml`: Jekyll build for plain-HTML sites

Main page will be shown at `index.html`.

Other deployment services:
- Netlify (`netlify.toml`)
- Vercel (`vercel.json`)

## Project structure

```
├── index.html          # the whole site
├── css/
│   └── site.css        # the new minimal stylesheet
├── libs/
│   └── Vo_Hung_Resume.pdf
├── images/             # legacy assets from the old Bootstrap site
├── css/bootstrap.min.css, css/styles.css, js/, font-awesome/
│                       # legacy — safe to delete once the redesign is confirmed
└── README.md
```

## TODO

- [ ] Replace the placeholder LinkedIn URL and email in `index.html` (marked with `<!-- TODO -->`)
- [ ] Delete legacy Bootstrap/Font Awesome/jQuery files once happy with the redesign
- [ ] Optionally add a favicon
