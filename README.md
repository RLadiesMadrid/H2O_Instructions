# H2O Instructions

Instructions to get started on the WeCode H2O Workshop.

In this workshop R will only be a requirement if you want to follow the R code, otherwise you can still do the workshop with the H2O Flow feature, you won't need any R dependency for that.

H2O Flow is a feature which lets you do some basic ML directly from your browser with a Java backend, so please be sure to install Java.

## Requirements

1. Operating Systems:

  - Windows 7 or later
  - OS X 10.9 or later
  - Ubuntu 12.04
  - RHEL/CentOS 6 or later
  
2. Languages:

  - Java is always required. Supported versions include:
    - Java 7 or later. Note: Java 9 is released, but is **not currently supported**. 
  - To run the H2O binary using either the command line, R, or Python packages, only 64-bit JRE is required.
  
3. Browser: 

  - An internet browser is required to use H2O’s web UI, Flow. 
  - Latest version of Chrome, Firefox, Safari, or Internet Explorer.
  
## Install Java Dependecies

You can find a download file in the [Oracle Website](https://java.com/en/download/).

If you are using OSX with Homebrew run

```
$ brew update
$ brew tap caskroom/cask
$ brew install Caskroom/cask/java
```

## Install R

Download R directly from [CRAN](https://cran.r-project.org/).

### Install RStudio

RStudio makes R easier to use. It includes a code editor, debugging & visualization tools. Download the [free version](https://www.rstudio.com/products/rstudio/download/). 

Be aware RStudio is only an IDE, you need to install R in order to use RStudio.

## Install H2O

### To use it standalone (without R)

Install H2O last stable version directly from their [website](http://h2o-release.s3.amazonaws.com/h2o/rel-wolpert/2/index.html).

### R Package

To install the R package run the following code and you'll get a clean version of the latest package:

```r
# The following two commands remove any previously installed H2O packages for R.
if ("package:h2o" %in% search()) { detach("package:h2o", unload=TRUE) }
if ("h2o" %in% rownames(installed.packages())) { remove.packages("h2o") }

# Next, we download packages that H2O depends on.
pkgs <- c("RCurl","jsonlite")
for (pkg in pkgs) {
  if (! (pkg %in% rownames(installed.packages()))) { install.packages(pkg) }
}

# Now we download, install and initialize the H2O package for R.
install.packages("h2o", type="source", repos="http://h2o-release.s3.amazonaws.com/h2o/rel-wolpert/1/R")

# For more: http://h2o-release.s3.amazonaws.com/h2o/rel-lambert/5/docs-website/Ruser/Rinstall.html
```

## Check your dependencies

- Check your Java version with `$ java -version` from the command line.

```bash
java version "1.8.0_144"
```

- Check your R version with `$ R --version` form the command line or opening RStudio and taking a look at the console.

```bash
R version 3.4.3 (2017-11-30)
```

- Check your H2O installation with `$ java -jar h2o.jar` from the command line.

- Check your R H2O package with from the R console.

```r
library(h2o)
h2o.init()
```

## Data

We will try to cover two ML algorithms. For that we will use two different data sets (last one is a stopwords dataset to improve the algorithm), please be sure to download them before the workshop:

- [Airlines data](https://raw.githubusercontent.com/h2oai/h2o-tutorials/master/tutorials/data/allyears2k.csv)
- [Amazon Reviews](https://s3.amazonaws.com/tomk/h2o-world/megan/AmazonReviews.csv)
- [Stopwords for NLP](https://raw.githubusercontent.com/h2oai/h2o-tutorials/master/h2o-world-2017/nlp/stopwords.csv)
