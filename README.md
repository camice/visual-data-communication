# Visual Data Communication: designing figures with purpose in R and Python

Course materials for the Cambridge Centre for Research Informatics Training (CRIT) course on data visualisation.

The rendered site is published at <https://cambiotraining.github.io/visual-data-communication/>.

## Structure

- `index.md`, `setup.md`, `design-process.qmd`: welcome pages.
- `materials/`: the ten practical chapters, each with R and Python tabs.
- `reference/`: figure checklist, code recipes and the critique gallery.
- `materials/data/`: course datasets. `data_visual-data-communication.zip` (repository root) is the download linked from the Setup page.
- `materials/images/`: static teaching figures. `materials/images/generated/` holds Python multi-panel figures written during rendering.

## Rendering locally

The site uses Quarto with the knitr engine, so R and Python chunks run in the same document through reticulate.

1. Install R packages: `tidyverse`, `patchwork`, `scales`, `colorspace`, `Hmisc`, `reticulate`, `rmarkdown`.
2. Install Python packages: `pandas`, `plotnine` (version 0.15 or later).
3. Point reticulate at your Python, for example `export RETICULATE_PYTHON=$(which python3)`.
4. Run `quarto render`.

Rendering uses `freeze: auto`, so the `_freeze/` folder must be committed. GitHub Actions then publishes the site from the frozen results without needing R or Python.

## Python and composed figures

plotnine figures combined with `|` and `/` cannot be displayed inline by knitr. In those chunks, the visible code is shown with `eval: false`, and a hidden chunk saves the figure to `materials/images/generated/`, which is then included as an image. Learners running the code in Jupyter, VS Code or a script see the figure directly.

## Licence

These materials are released under a [CC BY 4.0](LICENSE.md) licence. This version (2026) is a redesign by Camice Revier of the original course by Martin van Rongen, Hugo Tavares and Matt Castle. Earlier versions are kept in the Git history.
