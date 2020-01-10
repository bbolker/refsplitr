# refsplitr <img src="man/figures/refsplitrhex.png" height="200" align="right">

[![Project Status: Active The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)    [![Build Status](https://travis-ci.org/embruna/refsplitr.svg?branch=master)](https://travis-ci.org/embruna/refsplitr)    [![](https://badges.ropensci.org/256_status.svg)](https://github.com/ropensci/onboarding/issues/256)   [![Coverage Status](https://coveralls.io/repos/github/embruna/refsplitr/badge.svg?branch=master)](https://coveralls.io/github/embruna/refsplitr?branch=master)

refsplitr: an R package for processing Web of Science Records and mapping georeferenced coauthorship networks

refsplitr (v1.0) is an R package to organize, disambiguate, geocode, and visualize reference records downloaded from the Clarivate Web of Science (WOS). The WOS is a toll-access literature and citation database that indexes articles from ~12,000 academic journals. WOS records  include a diversity of data about each article (e.g., article title, journal name, author names, author addresses, number of times the article has been cited, funding sources), making them very useful for studying patterns of scientific productivity, coauthorship, research impact, and other Science of Science topics. Because bulk WOS records and API access to the WOS are very expensive, researchers at WOS-subscribing institutions often gather data by conducting WOS searches and downloading reference records in batches. However, this requires a cumbersome process of extracting, merging, and correcting data from the downloaded records prior to conducting any analyses. refsplitr will rapidly merge and process reference data files downloaded from the WOS, and then process and organize them in a format amenable for use in scientometric, social network, and Science of Science analyses. 

Support for the development of refsplitr was provided by grants from the [University of Florida Center for Latin American Studies](http://www.latam.ufl.edu/) and the [University of Florida Informatics Institute](https://informatics.institute.ufl.edu/).

## Installation

You can install the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("embruna/refsplitr")
```

## Workflow

There are four steps in the `refsplitr` package's workflow:   
1. Importing and tidying Web of Science reference records
2. Author name disambiguation and parsing of author addresses
3. Georeferencing of author institutions
4. Data visualization

This is done using a series of simple commands; an example of this simple workflow is provided below:

``` r
# load the Web of Science records into a dataframe
dat1 <- references_read(data = system.file("extdata", "example_data.txt", package = "refsplitr"), dir = FALSE)

# load the Web of Science records into a dataframe
dat1 <- references_read(data = system.file("extdata", "example_data.txt", package = "refsplitr"), dir = FALSE)
# disambiguate author names and parse author address
dat2 <- authors_clean(references = dat1)

# after revieiwng disambiguation, merge any necessary corrections
dat3 <- authors_refine(dat2$review, dat2$prelim)

# georeference the author locations
dat4 <- authors_georef(dat3)

# generate a map of coauthorships; this is only one of the five possible visualizations  
plot_net_address(dat4$addresses)
```

**We welcome any suggestions for package improvement or ideas for features to include in future versions.** If you have Issues, Feature Requests and Pull Requests, [here is how to contribute](https://github.com/embruna/refsplitr/blob/master/CONTRIBUTING.md). We expect everyone contributing to the package to abide by our [Code of Conduct](https://github.com/embruna/refsplitr/blob/master/CODE_OF_CONDUCT.md). 

<center>
<img src="man/figures/coauthor_connections_BITR.png" height="400">
</center>
<center>
Map of georeferenced article coauthorships generated with refsplitr.
</center>


## Contributors
* [Auriel Fournier](https://github.com/aurielfournier), Porzana Solutions
* [Matt Boone](https://github.com/birderboone), Porzana Solutions
* [Forrest Stevens](http://forreststevens.com/teaching/research.html), University of Louisville
* [Emilio M. Bruna](https://github.com/embruna), University of Florida

## Citation

Auriel M.V. Fournier Developer, Matthew E. Boone Developer, Forrest R.
  Stevens Developer and Emilio M. Bruna Developer (2018). refsplitr:
  Clarivate Web of Knowledge / Web of Science  Reference Data Tools. R package version
  0.6.
  
    @Manual{,
    title = {refsplitr: Thomson Reuters Web of Knowledge/Science Reference Data Tools},
    author = {Auriel M.V. Fournier Developer and Matthew E. Boone Developer and Forrest R. Stevens Developer and Emilio M. Bruna Developer},
    year = {2018},
    note = {R package version 0.6},
    }
    
_Note regarding package development history_: The early development of `refsplitr`- initially known as `refnet` - was by Forrest Stevens and Emilio M. Bruna and was done on [r-forge](https://r-forge.r-project.org/projects/refnet/). In December 2017 Bruna moved it to Github and hired [Porzana Solutions](https://github.com/aurielfournier) to finalize the package and prepare it for submission to CRAN.  _Please make all suggestions for changes via this Github repository - do not make a repo mirror of the R-forge version._

[![ropensci_footer](https://ropensci.org/public_images/ropensci_footer.png)](https://ropensci.org)
