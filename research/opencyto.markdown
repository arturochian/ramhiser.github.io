---
title: "OpenCyto: An Open Source Infrastructure for Scalable, Robust, Reproducible, and Automated, End-to-End Flow Cytometry Data Analysis"
comments: false
sharing: true
footer: true
---

* **Title**. [OpenCyto: An Open Source Infrastructure for Scalable, Robust, Reproducible, and Automated, End-to-End Flow Cytometry Data Analysis](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003806)

* **Authors**. [Finak, G.](https://github.com/gfinak), Frelinger J., Jiang, W.,
  Newell, E., [Ramey, J.]((http://ramhiser.com)), Davis, M., Kalams, S., de
  Rosa, S., and [Gottardo, R.](http://www.rglab.org/)

* **Abstract**. Flow cytometry is used increasingly in clinical research for
    cancer, immunology and vaccines. Technological advances in cytometry
    instrumentation are increasing the size and dimensionality of data sets,
    posing a challenge for traditional data management and analysis. Automated
    analysis methods, despite a general consensus of their importance to the
    future of the field, have been slow to gain widespread adoption. Here we
    present OpenCyto, a new BioConductor infrastructure and data analysis
    framework designed to lower the barrier of entry to automated flow data
    analysis algorithms by addressing key areas that we believe have held back
    wider adoption of automated approaches. OpenCyto supports end-to-end data
    analysis that is robust and reproducible while generating results that are
    easy to interpret. We have improved the existing, widely used core
    BioConductor flow cytometry infrastructure by allowing analysis to scale in
    a memory efficient manner to the large flow data sets that arise in clinical
    trials, and integrating domain-specific knowledge as part of the pipeline
    through the hierarchical relationships among cell populations. Pipelines are
    defined through a text-based csv file, limiting the need to write
    data-specific code, and are data agnostic to simplify repetitive analysis
    for core facilities. We demonstrate how to analyze two large cytometry data
    sets: an intracellular cytokine staining (ICS) data set from a published HIV
    vaccine trial focused on detecting rare, antigen-specific T-cell
    populations, where we identify a new subset of CD8 T-cells with a
    vaccine-regimen specific response that could not be identified through
    manual analysis, and a CyTOF T-cell phenotyping data set where a large
    staining panel and many cell populations are a challenge for traditional
    analysis. The substantial improvements to the core BioConductor flow
    cytometry packages give OpenCyto the potential for wide adoption. It can
    rapidly leverage new developments in computational cytometry and facilitate
    reproducible analysis in a unified environment.
