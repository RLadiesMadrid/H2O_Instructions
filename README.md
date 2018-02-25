# H2O Instructions

Instructions to get started on the WeCode H2O Workshop.

In this workshop R only be a requirement if you want to follow the R code, otherwise you can still do the workshop with the H2O Flow feature, you won't need any R dependency for that.

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

## Install H2O

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

- Check your H2O installation with `$ java -jar h2o.jar` from the command line.

- Check your R H2O package with 

```r
library(h2o)
h2o.init()
```

from the R console.
