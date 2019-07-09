---
title: EmoRy Coding Club master document 
author: |
 | Matt Malishev*, Desiree De Leon & Hasse Walum     
 |  
 | _Emory University, 1510 Clifton Road NE, Atlanta, GA, USA, 30322_
header-includes: \usepackage{float}
fontsize: 12
geometry: margin=1in
documentclass: article
linkcolor: blue
urlcolor: blue
citecolor: red
always_allow_html: yes
output:
  html_document:
    highlight: tango
    code_folding: show
    toc: yes
    toc_depth: 2
    number_sections: no
    toc_float: yes
    self_contained: false
    keep_md: true
  pdf_document:
    includes:
      in_header: # add .tex file with header content
    highlight: tango
    template: null
    toc: yes
    toc_depth: 3
    number_sections: false
    fig_width: 4
    fig_height: 5
    fig_caption: true
    df_print: tibble 
    citation_package: biblatex # natbib
    latex_engine: xelatex #pdflatex # lualatex
    keep_tex: true # keep .tex file in dir 
inludes:
  before_body: before_body.tex
subtitle: 
tags:
- nothing
- nothingness
params: 
  # dir: "/Users/malishev/Documents/Emory/admin/ecc/"
  date: !r Sys.Date()
  session: !r sessionInfo()  
  version: !r getRversion()
  email: "matthew.malishev@emory.edu"
  doi: https://github.com/darwinanddavis/EmoRyCodingClub
---

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({ TeX: { equationNumbers: {autoNumber: "all"} } });
</script>





\newpage   

Date: 2019-07-09  
R version: 3.5.0  
This document can be found at https://github.com/darwinanddavis/EmoRyCodingClub  

<!-- ____________________________________________________________________________ -->
<!-- start body -->

\newpage  

## Pre session  
1. assign 'hello world' to variable    
2. print to console  
3. run help page for 'print'  

## Lesson 1  

```r
install.packages()
head()
tail()
str()
plot()
df$Col1
df[, "Col1"]

# See call options for class
methods(class = "estUDm")
```

<!-- #### TOC     -->
<!-- What the session covers   -->
<!-- Dataset   -->
<!-- Showcase of what you'll learn by the end   -->



#### Importing Data

# airbnb data -------------------------------------------------------------


```r
require(readr)

# function for reading in zipped file (106 cols)
url <- "http://data.insideairbnb.com/united-states/ny/new-york-city/2019-06-02/data/listings.csv.gz"

url_read <- function(file_url) {
    con <- gzcon(url(file_url))
    txt <- readLines(con)
    return(read.csv(textConnection(txt)))
}

df <- url_read(url)  # read in data

# smaller csv file (16 cols)
url <- "http://data.insideairbnb.com/united-states/ny/new-york-city/2019-06-02/visualisations/listings.csv"
df <- read.csv(url)
# ------
```


# 3.2.3 A graphing template

We can keep re-using our ggplot code as a template to create new plots. The next sections will be about how to modify the mappings and aesthetics to visualize different parts of this dataset.

\  

# 3.3 Aesthetic mappings

![](admin/ggplot1.png)  

# 3.2.4 Exercises, 10 minutes (?)

1. Run `ggplot(data = mpg)`. What do you see?


```r
ggplot(data = mpg)
```

If we print `mpg` and find drv column, it's a bunch of weird values. What do they mean? Check the help documentation to find out. `?` works because this data set is built-in.

# Use `ggplot()`

* We'll do 1 together.
* Create new scatter plots with the data on your own
    * Explore at least 3 different variable relationships
    * Do 1 version of a presentable ggplot
    * Take the same ggplot and make change the aesthetics to make it an ugly ggplot
    * **Bonus points**: copy and paste the following code into one of your existing ggplots as an additional layer to make a very ugly ggplot! Run the plot to see what this produces. Then modify some of the arguments to make the plot look more acceptable!
      

* Ugly ggplot code courtesy of [Emily Riederer](https://gist.github.com/emilyriederer/2bf4f67d7e198f8359b61706c82e42ee)
\


\


\


 \
 


<!-- end body -->
<!-- ____________________________________________________________________________ -->

