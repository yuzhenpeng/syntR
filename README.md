
<!-- README.md is generated from README.Rmd. Please edit that file -->
syntR <img src="inst/figures/logo.png" align="right" width="120" height="135" />
================================================================================

syntR is an R package for the reproducible identification of synteny blocks and chromosomal rearrangments via comparison of two genetic maps. syntR implements an error-aware clustering algorithm specifically designed for the highly linear structure of comparative genetic map data. syntR can be used to identify synteny blocks using any type of ordered genetic markers. 

***Note: syntR is currently in active development.***

Installation
------------

You can install syntR from github with:

``` r
# install.packages("devtools")
devtools::install_github("ksamuk/syntR")
```

Example
-------

Find synteny blocks shared between *Helianthus petiolaris* and *Helianthus annus* (provided as example data):

``` r
# load the syntR library
library("syntR")

# load data
data(ann_pet_map)

# convert data to a single ordered scale
map_list <- make_one_map(ann_pet_map)

# find synteny blocks
synt_blocks <- find_synteny_blocks(map_list, max_clust_range = 2, max_nn_dist = 10, plots = TRUE)

# print the resulting synteny blocks dataframe
synt_blocks[[2]]]
```

Authors
------------
[Katherine Ostevik](http://www.kateostevik.com/) and [Kieran Samuk](https://ksamuk.github.io/).

See Also
-------
[GRIMM](http://grimm.ucsd.edu/GRIMM/) - A tool for analyzing rearrangements in pairs of genomes, including unichromosomal and multichromosomal genomes, and signed and unsigned data. 

[Flagel et al. 2018](https://www.biorxiv.org/content/early/2018/05/26/330159) - An example of a more formal model-based approach to a similar problem. 
