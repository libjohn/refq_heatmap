
<!-- README.md is generated from README.Rmd. Please edit that file -->

# refq\_heatmap

<!-- badges: start -->

<!-- badges: end -->

A quick survey of HTMLwidgets used for of interactive HTMLwidgets. Find
available options within the [widget
gallery](http://gallery.htmlwidgets.org/). Browse with “*CRAN Only*” set
to FALSE, and *Tag* = “heatmap”.

The top three packages include: `d3heatmap`, and `heatmaply`.

Another good option for stylized interactive charts are the [plotly
package](https://plot.ly/r/) (includes `ggplotly()` which can be used
with `ggplot2::geom_tile()`) and the [HighCharter
package](http://jkunst.com/highcharter/).

In the example below, install `d3heatmap`.

``` r
devtools::install_github("rstudio/d3heatmap")
```

## Load Library Packages

``` r
library(tidyverse)
library(d3heatmap)
```

## Example `d3heatmap` heatmaps

``` r
d3heatmap(mtcars, scale = "column", colors = "Spectral")
d3heatmap(mtcars[1:4,], scale = "column", colors = "Blues")

starwars %>% 
  column_to_rownames("name") %>% 
  select_if(is.numeric) %>% 
  drop_na() %>%
  d3heatmap(scale = "column",
            colors = "Greens")
```

<img src="output/hm_spectral.PNG" title="HeatMap with spectral color" alt="HeatMap with spectral color" style="display: block; margin: auto;" />

<br />

<img src="output/hm_blues.PNG" title="HeatMap blue" alt="HeatMap blue" style="display: block; margin: auto;" />

<br />

<img src="output/hm_greens.PNG" title="HeatMap green" alt="HeatMap green" style="display: block; margin: auto;" />
