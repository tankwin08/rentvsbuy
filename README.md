# Moat & Main — Rent vs Buy Calculator

**Moat & Main** is an interactive web calculator that helps you compare renting (and investing the savings in the S&P 500) vs buying a home and building equity.

Live demo: [https://tankwin08.github.io/rentvsbuy/](https://tankwin08.github.io/rentvsbuy/)

## Features

- **Monthly simulation** — Compares renter portfolio growth vs owner net equity year by year
- **Transparent methodology** — Interest-only owner costs, symmetric cash flow, upfront closing costs on both sides ([how we calculate](how_we_calculated.md))
- **City presets** — National median plus 9 major US metros
- **Visual chart** — 30-year comparison with break-even detection
- **Shareable scenarios** — URL encodes all slider values; use **Copy share link** to share
- **Advanced costs** — PMI, HOA, separate rent growth, optional tax deductions
- **Real vs nominal** — Inflation-adjusted results alongside headline numbers
- **Monthly cost snapshot** — Inspect owner vs renter monthly costs for any year (1–30)
- **No install** — Pure HTML/CSS/JavaScript, runs in any browser

## Usage

1. Open the calculator in your browser (locally or on GitHub Pages)
2. Pick a city preset or enter custom values
3. Adjust property, transaction, lifestyle, and return assumptions
4. Compare results at any year (1–30) or jump to break-even
5. Read [how_we_calculated.md](how_we_calculated.md) for the full methodology

## Local Development

```bash
git clone https://github.com/tankwin08/rentvsbuy.git
cd rentvsbuy
open index.html   # macOS — or open in any browser
```

No build step, no dependencies to install. Chart.js loads from jsDelivr CDN.

## Deployment (GitHub Pages)

This project is a static single-page app deployed from the `main` branch:

1. Push `index.html` and assets to `main`
2. In repo **Settings → Pages**, set source to **Deploy from branch → main / (root)**
3. Site is available at `https://<username>.github.io/rentvsbuy/`

For a custom domain (e.g. `moatmain.com`), add a `CNAME` file and configure DNS — GitHub Pages supports this at no extra cost.

## Project structure

```
index.html              # Full app (HTML, CSS, JS)
how_we_calculated.md    # Methodology documentation
README.md
LICENSE                 # Apache 2.0
```

## Contributing

Contributions welcome — especially calculation accuracy improvements, accessibility, and test coverage. Please open an issue or PR.

## License

Apache License 2.0 — see [LICENSE](LICENSE).

## Disclaimer

This calculator is for educational purposes only and does not constitute financial advice.
