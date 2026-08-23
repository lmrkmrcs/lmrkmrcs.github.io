# lmrkmrcs.github.io

My personal portfolio. Live at **[lmrkmrcs.github.io](https://lmrkmrcs.github.io)**.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222222?style=flat-square&logo=githubpages&logoColor=white)

---

## About

Leomark Marcus, final-year BSc (Hons.) Mathematics with Computer Graphics at Universiti Malaysia Sabah, looking for entry-level Data Analyst and Software Developer roles in Kota Kinabalu.

The site collects **eighteen projects**: eleven from the degree, covering deep learning, scientific visualisation, computer graphics, image processing, relational databases and data analysis, and seven built during an internship at a palm oil mill in Sabah. It also lists the eleven National Training Week 2026 certificates, each with its own page and a copy of the certificate.

## How it is built

Hand-written HTML, CSS and JavaScript. No framework, no build step, no npm packages, no bundler — `index.html` is served byte-for-byte by GitHub Pages on every push to `main`.

### Frontend

Everything the browser loads is these three files: `index.html` (~1,000 lines, every page and view), `style.css` (~440 lines), and one `<script>` block at the bottom of `index.html` (~30 lines).

- **Routing.** There's no client-side framework or router library. A self-invoking JS function reads `location.hash`, matches it against a list of known view ids (`uni`, `internship`, each certificate), and toggles the `hidden` attribute on the matching `<section>` — so `#/uni` or `#/cert-power-query` swaps content instantly with no page reload and no server round-trip. It listens for the `hashchange` event and re-renders on both that and initial load.
- **Layout.** CSS Grid with `repeat(auto-fill, minmax(...))` / `auto-fit` drives the responsive columns, so project cards, certificates and skill tiles reflow from one column on a phone up to four on a wide screen without any media-query breakpoints for the grid itself.
- **Design tokens.** Colours, radii and shadows are CSS custom properties on `:root` (`--navy`, `--teal`, `--glass`, `--blur`, etc.), so the palette and the frosted-glass look are defined once and reused everywhere.
- **Frosted glass.** Cards use `backdrop-filter: blur(16px) saturate(1.4)`. An `@supports not (backdrop-filter: …)` block swaps in a solid background for browsers that don't support it, and a `@media` query reduces blur radius on smaller screens for performance.
- **Responsive breakpoints.** A handful of `@media` rules collapse the two-up and multi-column grids to a single column and adjust spacing on narrow viewports.

### Backend

There isn't one. This is a fully static site — no server, no database, no API, no server-side rendering. All "data" (project descriptions, certificate details, contact info) is hand-written directly into `index.html`; there's nothing to fetch at runtime. That's a deliberate fit for a portfolio: content changes rarely, so a static file pushed straight to GitHub Pages is simpler and faster than standing up a backend for it.

## Structure

```
├── index.html          # every page and view
├── style.css           # all styling
└── assets/
    ├── projects/       # project screenshots
    ├── certs/          # certificate PDFs
    │   └── img/        # certificate images shown on the site
    ├── photo.jpg
    └── *.pdf           # resume and CV
```

## Running it locally

Any static server will do — it's plain HTML, CSS and JS with no build step to run first.

```bash
git clone https://github.com/lmrkmrcs/lmrkmrcs.github.io.git
cd lmrkmrcs.github.io
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Notes

The stylesheet link carries a content hash (`style.css?v=…`) so browsers pick up changes straight away instead of holding a cached copy.

Screenshots of the internship systems use generated data, not real company records.

## Contact

- [leomark.marcus0202@gmail.com](mailto:leomark.marcus0202@gmail.com)
- [linkedin.com/in/leomarkmarcus](https://www.linkedin.com/in/leomarkmarcus)
- [github.com/lmrkmrcs](https://github.com/lmrkmrcs)
