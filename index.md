---
title: "Welcome to the EmoRy Coding Club"
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
  word_document:
    highlight: tango
    keep_md: yes
    pandoc_args: --smart
    #reference: mystyles.docx
    toc: yes
inludes:
  before_body: before_body.tex
subtitle: 
tags:
- nothing
- nothingness
---

<!-- ---------------------------------------------------------------- -->
<!-- ----------------------- rmd settings --------------------------- -->
<!-- ---------------------------------------------------------------- -->



<!-- rmd settings -->


<!-- install packages -->


<!-- ---------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------- -->
\  
\  

<!-- ----------------------- overview --------------------------- -->
## Overview    
This page contains all the documents, links, and information for the monthly `R` coding club held in the Department of Biology, Emory University. We meet monthly and introduce new coding concepts and techniques in a casual working environment. The club is half lesson half workshop style and caters for all coding, `R`, and research levels.  
\  
\  
  
## Organisers  

**Matt Malishev, Department of Biology**    
**Desiree de Leon, Yerkes National Primate Research Center**  
**Hasse Walum, Yerkes National Primate Research Center**    

\  
\  
<!-- ----------------------- image --------------------------- -->
<div align="center"; text-align:center>
  <img src="img/mm.jpeg" style=width:33%>
  <img src="img/ddl.jpeg" style=width:33%>
  <img src="img/hw.jpg" style=width:33%>
</div>
<!-- ----------------------- image --------------------------- -->
\    

## Date for next session  
July 11, 2019      
4:00 - 6:00 PM       
\  

## Location   
Room 2052  
Wayne Rollins Building  
\  

<!--html_preserve--><div id="htmlwidget-54ceddfe9cc683e0739b" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-54ceddfe9cc683e0739b">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addMarkers","args":[33.79667,-84.32346,null,null,null,{"interactive":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},"Room 2052, Wayne Rollins Building",null,null,null,"Room 2052, Wayne Rollins Building",{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]}],"limits":{"lat":[33.79667,33.79667],"lng":[-84.32346,-84.32346]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->


<br>
\  
  
<!-- ----------------------- 1 before arrival --------------------------- -->
# Before you arrive
Everyone needs to have the following software and packages loaded before you come to the first session. That way, we can get straight into it.     
  

* [Install `R` from CRAN](https://www.r-project.org/). 
 + If you're asked to choose a CRAN mirror, just choose whichever is closest to your location.  
* [Install `RStudio` Desktop](https://www.rstudio.com/products/rstudio/download/)
* Install the `tidyverse` package and then load it by copying and pasting the following code into the *Console* of `RStudio` and then pressing *Enter* to execute it.


```r
install.packages("tidyverse")
install.packages("ggplot2")
library(tidyverse)
library(ggplot2)
```

\  
\  

### If you have used `R` previously, you can skip to ['Learning Objectives'](#sec3).  

\  
\  

<br>

<!-- ----------------------- 2 pre check --------------------------- -->
# Pre-work questions  
If you're brand new to `R` or coding, familiarise yourself with a few basic things about `R Studio` and coding in `R`. The exercise below should take less than 5 minutes.    

Once you have installed `R` and `R Studio`, copy and paste the code below into the `R Studio` *Console* (or try typing it out yourself) and press *Enter* to run it.  


```r
# Calculate something simple
2 + 2

# Calculate something using built-in constants
2 * pi
```

<br>

Use the *assignment operator*, `<-`, to create new objects in `R`


```r
a <- 2 + 2
b <- a * pi
c <- "Hello World"
```

And then print the objects in the console:


```r
a
b
c
```

<!-- ----------------------- 3 learning obj --------------------------- -->
<a id="sec3"></a>  

# Learning Objectives

Our first EmoRy Coding Club will be primarily targeted towards beginners, but we hope this will also useful for anyone who may already be familiar with base `R` and wanting better practice with the `tidyverse` package.  

1) Introducing beginners to the `RStudio` IDE
2) Doing some introductory plotting with `ggplot`

We will use the [R for Data Science](https://r4ds.had.co.nz/index.html) free online text to guide us through learning `R`.


<!-- ----------------------- image --------------------------- -->
<div align="center"; text-align:center>
  <img src="img/cover.png" style=width:33%>
</div>
<!-- ----------------------- image --------------------------- -->



<br>

<!-- ----------------------- 4 materials --------------------------- -->
# Materials

We'll be diving into [Ch 3, Data visualisation](https://r4ds.had.co.nz/data-visualisation.html) and working through Section 3.3.1.
\  

### The dataset    
We'll also be using [open-access data of housing listings from AirBnb](http://insideairbnb.com/new-york-city/) as our toy dataset. Once we've completed the above **R for Data Science exercises**, we'll repeat the plotting exercise using these data.      
\  

We'll be using this dataset for the rest of the club sessions, so feel free to explore it in your own time.      
\  
\  

<!-- ----------------------- image --------------------------- -->
<div align="center"; text-align:center>
  <img src="img/nyc.jpg" style=width:100%>
</div>
<!-- ----------------------- image --------------------------- -->  
  

This is a really big data set (it has ~50k rows !!), so it will take a moment to run. To import the AirBnb data from the URL, copy and paste the lines of code below in your `R` console and press *Enter*.   


```r
require(readr)
url <- "http://data.insideairbnb.com/united-states/ny/new-york-city/2019-06-02/visualisations/listings.csv"

df_full <- read_csv(url)
glimpse(df_full)

# smaller csv file (16 cols)
url <- "http://data.insideairbnb.com/united-states/ny/new-york-city/2019-06-02/visualisations/listings.csv"
df_full <- read_csv(url)
df <- df_full[df_full$id < 1e+06, ]  # truncate dataset 
df

head(df[, 1:5])
```

If everything worked correctly, you should see the below ouput printed in your `R` console.  


```
    id                                             name host_id   host_name neighbourhood_group
1 2539               Clean & quiet apt home by the park    2787        John            Brooklyn
2 2595                            Skylit Midtown Castle    2845    Jennifer           Manhattan
3 3647              THE VILLAGE OF HARLEM....NEW YORK !    4632   Elisabeth           Manhattan
4 3831                  Cozy Entire Floor of Brownstone    4869 LisaRoxanne            Brooklyn
5 4989 Great 1 bdrm. apartment in the PERFECT location!    7118  New-Yorker           Manhattan
6 5022 Entire Apt: Spacious Studio/Loft by central park    7192       Laura           Manhattan
```


  
