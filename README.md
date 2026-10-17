# Robotics in Motion — Interactive Plotly Presentation

**Creation date:** October 17, 2026

An interactive 6-slide presentation exploring three simulated drone navigation routes. It includes two Plotly charts (a rotatable 3D chart and a hoverable distance comparison chart).

## Publish with GitHub Pages
1. Create a **public** repository named `robotics-plotly-presentation` on GitHub.
2. Upload `index.html` to the **root** of the repository. You may also upload `robotics_routes.Rmd`, `styles.css`, and `README.md`.
3. In **Settings → Pages**, select **Deploy from a branch**, then **main** and **/(root)**, and click **Save**.
4. The URL will be `https://YOUR_USERNAME.github.io/robotics-plotly-presentation/` after Pages finishes deploying.

The ready-to-publish `index.html` embeds Plotly JavaScript and works without an internet connection except for the optional Google font, which falls back gracefully.

## Rebuild from R Markdown
Install R, RStudio (optional) and these packages:

```r
install.packages(c("rmarkdown", "plotly", "knitr", "htmlwidgets"))
rmarkdown::render("robotics_routes.Rmd")
```

This renders an `ioslides` presentation containing the R-created Plotly widgets. `styles.css` should remain beside the `.Rmd` file.

The provided `index.html` is a separately prepared offline-ready web edition of the same R Markdown material and equations, with custom slide navigation. It was not knitted by R in this environment.

## Source / methods
No external dataset. Simulated route equations:

- Direct: `(10t, 0, 1.2)`
- Lateral detour: `(10t, 2.1 sin(pi t), 1.2)`
- Vertical bypass: `(10t, 0, 1.2 + 2.9 sin(pi t))`

`t` ranges from 0 to 1. A cylindrical obstacle of radius 1.15 km and height 2.8 km is centered at `(5, 0)`. The path length calculation sums Euclidean distances between consecutive simulated points.

**Note:** A demonstration of geometry only, not operational drone-safety guidance.
