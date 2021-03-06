---
layout: post
title: "Setting Up the Development Version of R"
date: 2012-08-28 20:42
comments: true
categories: [R, workflow]
---

My [coworkers](http://rglab.org) at [Fred Hutchinson](http://fhcrc.org) regularly use
the development version of [R](http://www.r-project.org/) (i.e., `R-devel`) and have urged me to do the same.
This post details how I have set up the development version of R on our Linux server,
which I use remotely because it is much faster than my Mac.

First, I downloaded the `R-devel` source into `~/local/`, which is short for `/home/jramey/local/` via Subversion, configured my
installation, and compiled the source. I recommend these [Subversion tips](http://developer.r-project.org/SVNtips.html)
if you are building from source. Here are the commands to install `R-devel`.

{% highlight bash %}
svn co https://svn.r-project.org/R/trunk ~/local/R-devel
cd ~/local/R-devel
./tools/rsync-recommended
./configure --prefix=/home/jramey/local/
make
make install
{% endhighlight %}

The third command downloads the recommended R packages and is crucial because the source for the recommended R packages is not included in the SVN repository. For more about this, [go here](http://cran.r-project.org/doc/manuals/R-admin.html#Using-Subversion-and-rsync).

We have the release version (currently, it is 2.15.1) installed in `/usr/local/bin`. But the goal here is to give priority to `R-devel`. So, I add the following to my `~/.bashrc` file:

{% highlight bash %}
PATH=~/local/bin:$PATH
export PATH

# Never save or restore when running R
alias R='R --no-save --no-restore-data --quiet'
{% endhighlight %}


Notice that the last line that I add to my `~/.bashrc` file is to load `R-devel` quietly without saving or restoring.

Next, I install the R packages that I use the most.

{% highlight r %}
install.packages(c('devtools', 'ProjectTemplate', 'knitr', 'ggplot2', 'reshape2',
                   'plyr', 'Rcpp', 'mvtnorm', 'caret'), dep = TRUE)
{% endhighlight %}

Then, I update my `.Rprofile` file, which I keep in a Github gist.

{% gist 1378639 .bash_profile %}

Finally, my [coworkers](http://rglab.org) focus on [flow cytometry](http://en.wikipedia.org/wiki/Flow_cytometry) data, and our group
maintains several [Bioconductor](http://www.bioconductor.org/) packages related to this type of data. To install the majority of
them, we simply install the [flowWorkspace](http://www.bioconductor.org/packages/2.10/bioc/html/flowWorkspace.html) package in R:

{% highlight r %}
source("http://bioconductor.org/biocLite.R")
biocLite("flowWorkspace")
{% endhighlight %}

