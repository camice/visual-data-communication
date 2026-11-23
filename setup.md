---
number-sections: false
---

# Data & setup {.unnumbered}

## Data

All the data used in the course comes as a single zip file. Download it and unzip it into the folder you will work in, so that you have a `data` folder next to your scripts.

<a href="https://github.com/camice/visual-data-communication/raw/main/data_visual-data-communication.zip">
  <button class="btn"><i class="fa fa-download"></i> Download data</button>
</a>

The folder contains:

| File | What it contains |
|---|---|
| `penguins.csv` | Bill, flipper and body measurements for 344 penguins of three species |
| `gapminder_2010.csv` | Income, health and population indicators for 167 countries in 2010 |
| `gapminder_1960_2010.csv` | The same indicators for every year from 1960 to 2010 |
| `finches.csv` | Beak and body measurements for Darwin's finches |

A suggested folder layout:

```
my-figures/
    data/
        penguins.csv
        ...
    figures/        (save your figures here)
    my_script.R     (or my_script.py)
```

## Software

You only need **one** of the two languages. Choose whichever you use in your own work.

::: {.panel-tabset group="language"}
## R

1. Install [R](https://cran.r-project.org/) (version 4.2 or later).
2. Install [RStudio Desktop](https://posit.co/download/rstudio-desktop/).
3. Open RStudio and run this in the console to install the packages:

```r
install.packages(c("tidyverse", "patchwork", "scales", "colorspace", "Hmisc"))
```

4. Check everything works:

```r
library(tidyverse)
ggplot(mtcars, aes(x = wt, y = mpg)) + geom_point()
```

If you see a scatter plot, you are ready.

## Python

1. Install Python 3.10 or later, from [python.org](https://www.python.org/downloads/) or with [Miniforge](https://github.com/conda-forge/miniforge).
2. Install [Visual Studio Code](https://code.visualstudio.com/) with the Python extension, or use JupyterLab.
3. In a terminal, install the packages:

```bash
pip install pandas plotnine
```

or, with conda:

```bash
conda install -c conda-forge pandas plotnine
```

4. Check everything works:

```python
import pandas as pd
from plotnine import ggplot, aes, geom_point
from plotnine.data import mtcars

p = ggplot(mtcars, aes(x="wt", y="mpg")) + geom_point()
p.show()
```

If you see a scatter plot, you are ready.
:::

::: {.callout-note}
#### Can't install software?

You can follow the R materials in [Posit Cloud](https://posit.cloud/) and the Python materials in [Google Colab](https://colab.research.google.com/) through a web browser. Upload the data folder to your project first.
:::

## Why ggplot2 and plotnine?

Both packages implement the same *grammar of graphics*, so the code looks almost identical in the two languages. The main difference is that Python puts column names in quotes:

::: {.panel-tabset group="language"}
## R

```r
ggplot(penguins, aes(x = bill_length_mm, y = bill_depth_mm)) +
  geom_point()
```

## Python

```python
(ggplot(penguins, aes(x="bill_length_mm", y="bill_depth_mm"))
 + geom_point())
```
:::

Learn the ideas once, and you can use them in either language.
