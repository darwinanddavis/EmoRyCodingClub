---
Title: "Lesson 2"
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
params: 
  lesson: !r paste0("Lesson ",2)  
---



\

<!-- install packages -->


<!-- ____________________________________________________________________________ -->
<!-- ____________________________________________________________________________ -->
<!-- ____________________________________________________________________________ -->
<!-- start body -->

# Lesson 2: Reading data and more plotting  
\  

Functions for Lesson 2    

\  

Packages for Lesson 2      

\  

# Agenda  


# Agenda

We'll be using [Ch 3 Data visualisation in `R` for Data Science](https://r4ds.had.co.nz/data-visualisation.html).  
Section 3.1.1.     

* Do first problem set
* Read in data file  
* Set working directory `here`  
* Facets  


\  

# Do first problem set

Recreate this plot using lesson 1 content    


```r
ggplot()
```

# Read in .csv data file  


```r
require(here)
getwd()
here()

read_csv("data.csv")
```

