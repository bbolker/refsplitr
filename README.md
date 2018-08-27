# refnet


# refnet <img src="man/figures/refnethex.png" height="200" align="right">

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)

refnet: an R package for processing Web of Science Records and mapping georeferenced coauthorship networks

refnet (v1.0) is an R package to read, organize, geocode, analyze, and visualize Clarivate Web of Knowledge/Web of Science, ISI, and SCOPUS format reference data files for scientometric, social network, and Science of Science analyses. The original package development was by Forrest Stevens and Emilio M. Bruna and was on r-forge (https://r-forge.r-project.org/projects/refnet/); in December 2017 Bruna moved it to Github to facilitate updating the package for submission to CRAN.  <b>Please make all future changes via this Github repo! Do *not* make a repo mirror of the R-forge version.</b> 

## Installation

You can install the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("embruna/refnet2")
```

## Workflow

```{r example, eval=FALSE}
references_read()
authors_clean()
authors_refine()
authors_georef()
```

Issues, Feature Requests and Pull Requests Welcome


## Contributors
* [Auriel Fournier](https://github.com/aurielfournier)
* [Forrest Stevens](http://forreststevens.com/teaching/research.html)
* [Matt Boone](https://github.com/birderboone)
* [Emilio Bruna](https://github.com/embruna)


## Citation

Auriel M.V. Fournier Developer, Forrest R.
  Stevens Developer, Matthew E. Boone Developer
  and Emilio Bruna Developer (2018). refnet:
  Clarivate Web of Knowledge / Web of Science and
  ISI Reference Data Tools. R package version
  0.6.
  
    @Manual{,
    title = {refnet: Thomson Reuters Web of Knowledge/Science and ISI Reference Data Tools},
    author = {Auriel M.V. Fournier Developer and Forrest R. Stevens Developer and Matthew E. Boone Developer and Emilio Bruna Developer},
    year = {2018},
    note = {R package version 0.6},
  }
