<!-- this enables math encoding in the knitted documents  -->
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({ TeX: { equationNumbers: {autoNumber: "all"} } });
</script>
Date: 2019-10-20
R version: 3.5.0
\*Corresponding author: your email here

Overview
========

This document showcases how to create and use `RMarkdown` documents.

You can write in-line `code` if you want to differentiate between when you are typing normally or highlighting `model parameters`, for example.

Equations like this *t*′=*γ*(*t* − *v**x*/*c*<sup>2</sup>), to appear within text lines.

Create links to your [website](https://github.com/darwinanddavis).

Make footnotes[1].

Use different headings
----------------------

### Like this subheading

Just like , but *more versatile*.
=================================

Define equations
----------------

Accordingly, we write the eigenfunction of a spinless particle as the superposition of plane wave states of momentum (*π*) and energy (*E**j*) having amplitudes *a*(*π*, *E**j*)

$$  
\\phi n(r,t) =  
\\sum\_{i, j} a(p\_{i},E\_{j})
e^{
\\frac{i}
{h}
(p\_{i} \\cdot r - E\_{j}t) 
}
$$
    

Embed images/gifs:
------------------

![Great power is pretty boring](img/opm.jpg).

Create, alter, and embed plots
------------------------------

![](Lesson5_rmd_files/figure-markdown_github/unnamed-chunk-1-1.png)

Figure 1. Example of a stock plot embedded into a PDF from RMarkdown.

Show plots with associated code
-------------------------------

``` r
require(viridis)
bm <- 0
par(las = 1, bty = "n")
xlim <- c(-5, 5)
ylim <- c(0, 0.5)
set.seed(12)
N <- 2000
rr <- rnorm(N)
rr2 <- rnorm(N^2)
rr3 <- rnorm(N + 0.3)
rrd <- density(rr)
rrd2 <- density(rr2)
rrd3 <- density(rr3)
main <- paste0(N, " points but plot better")
xlab <- "Points in space"
if (bm == 1) {
    layout(matrix(c(rep(1, 3), 2:4), 2, 3, byrow = TRUE))
    sc <- 1
    plot(rr, las = 1, bty = "n", col = adjustcolor(viridis(N), 0.5), pch = 20, cex = runif(10, 1, 5), 
        main = main, xlab = xlab)
    for (r in list(rrd, rrd2, rrd3)) {
        plot(r, xlim = xlim, ylim = ylim, main = "")
        polygon(r, col = adjustcolor(viridis(250)[sc], 0.5), border = viridis(250)[sc])
        sc <- sc + 100
    }
} else {
    par(mfrow = c(1, 1))
    plot(rr, las = 1, bty = "n", col = adjustcolor(viridis(N), 0.5), pch = 20, cex = runif(10, 1, 5), 
        main = main, xlab = xlab)
}
```

![](Lesson5_rmd_files/figure-markdown_github/unnamed-chunk-2-1.png)

Figure 2. Example of a plot with improved graphics and its associated code embedded into a PDF from RMarkdown.

And tables
----------

Table 1. Definitions of model parameters for individual hosts and **parasites**. Dimensions and units: -, dimensionless; cm, centimetres; J, Joules; L, length.

| Parameter | Definition                    | Dimension<br/>(unit) |
|:---------:|:------------------------------|:--------------------:|
|    *L*    | structural length             |          cm          |
|    *ee*   | scaled reserve density        |  J (cm<sup>3</sup>)  |
|    *D*    | host development              |          ---         |
|    *RH*   | energy in reproduction buffer |           J          |

Embed code from different languages
-----------------------------------

### This is `R` code

``` r
if (pck == 1) {
    p <- c("rJava", "RNetLogo")
    remove.packages(p)
    # then install rJava and RNetLogo from source
    install.packages("rJava", repos = "https://cran.r-project.org/")
    install.packages("RNetLogo", repos = "https://cran.r-project.org/")
}
```

### `shell/bash`

``` bash
echo "Hello Bash!"  
pwd # check working dir
git init # initialise git
```

### Octave (and MATLAB from the `RMatlab` package).

[`RMatlab documentation`](https://cran.r-project.org/web/packages/R.matlab/index.html).

``` octave
b = [4; 9; 2] # Column vector
A = [ 3 4 5;
      1 3 1;
      3 5 9 ]
x = A \ b     # Solve the system Ax = b
```

### HTML

``` html
<!-- links-->
        <div class="footer">
            <a href="dd_feed.html" 
            class="transition fade_in">
                Latest post
            </a>
            &nbsp; &nbsp; &nbsp;
            <a href="dd_contact.html" 
            class="transition fade_in">
                Contact
            </a>
            &nbsp; &nbsp; &nbsp;
            <a href="dd_subscribe.html"
            class="transition fade_in">
                Subscribe
            </a>
        </div>
```

### CSS

``` css
body {
  color: red;
}
```

### Javascript to access `html` and `css`

``` js
$('.title').css('color', 'red')
```

### Python

``` python
x = 'hello, python world!'
print(x.split(' '))
```

### Here's a complete list of available languages

``` r
names(knitr::knit_engines$get())
```

    ##  [1] "awk"       "bash"      "coffee"    "gawk"      "groovy"    "haskell"   "lein"      "mysql"    
    ##  [9] "node"      "octave"    "perl"      "psql"      "Rscript"   "ruby"      "sas"       "scala"    
    ## [17] "sed"       "sh"        "stata"     "zsh"       "highlight" "Rcpp"      "tikz"      "dot"      
    ## [25] "c"         "fortran"   "fortran95" "asy"       "cat"       "asis"      "stan"      "block"    
    ## [33] "block2"    "js"        "css"       "sql"       "go"        "python"    "julia"     "sass"     
    ## [41] "scss"

[1] Where the footnote goes here and it is automatically formatted