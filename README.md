# lmrkmrcs.github.io

My personal portfolio. Live at **[lmrkmrcs.github.io](https://lmrkmrcs.github.io)**.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222222?style=flat-square&logo=githubpages&logoColor=white)

---

## About

Leomark Marcus, final-year BSc (Hons.) Mathematics with Computer Graphics at Universiti Malaysia Sabah, looking for entry-level Data Analyst and Software Developer roles in Kota Kinabalu.

The site collects **eighteen projects**: eleven from the degree, covering deep learning, scientific visualisation, computer graphics, image processing, relational databases and data analysis, and seven built during an internship at a palm oil mill in Sabah. It also lists the eleven National Training Week 2026 certificates, each with its own page and a copy of the certificate.

## How it is built

Hand-written HTML and CSS. No framework, no build step, no dependencies. Push to `main` and GitHub Pages serves it.

Project and certificate detail pages are handled by a small hash router at the bottom of `index.html`. A URL like `#/uni` or `#/cert-power-query` hides the home page and reveals the matching `<section>`, so the whole site stays a single file without a full page load between views.

The layout uses CSS Grid with `auto-fit`, so it reflows from one column on a phone to four on a wide screen. Surfaces are frosted glass (`backdrop-filter`), with solid fallbacks for browsers that do not support it.

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

Any static server will do, since it is only HTML and CSS.

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
