---
title       : Visual Software Analytics
subtitle    : Using R to Explore Software Metrics of JUnit(tm)
author      : Peter Huber
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

Software is built from Source Code, like Classes which are organized in Packages or Modules. 
To assess the Quality of Software, certain Metrics [1] are computed to be able to do quantitative Analysis.
Metrics are computed on different Levels describing an aspect of a thing, for instance the number of lines of code of a method, or interdependencies between things, like the number of packages a packages depends on (inlude-relations). These are basic metrics which can be computed from source code alone.
"Quality of Software" is finaly a abstract term which is used to describe higher level aspects so called "ilities" like
Maintainability, Testability, Traceability, Modularity, etc which see the Software as a whole. Based on the basic metrics you can try to compute certain index-values for these ilities, for instance a Maintainability-Index [2].

This Project provides means to do some exploratory Analysis to a Java Software Library called "JUint" [3] in Terms of the Basic Metrics for the Java Classes of JUnit. This is usually a first step in the assessment of Source Code to get a first impression of potential hot spots / code smells. It gives direction to further investigation steps.

Actually this is a feasibility study to show that the processing pipeline as described on the next slide works and could be used for Visual Software Analytics.

--- .class #id 

## Methods

# Data Collection

Data was collected in three steps

1. Apply inFamix[4] Parser to the source Code of JUnit. Result is a File in MSE-Format [5]

2. Parse MSE-File and build two R data.frames for Java Class and Java Package Data. Code in my github Repository "SoftwareAnalyticsWithR" was used [6] that I created during a openHPI MOOC class [7]

3. Provide these data.frames as input files to the shiny app[8]

# Exploratory Analysis

The shiny app allows the user to select a Metric and displays a treemap of the Metric grouped per Package, i.e. all classes that belong to a Package contribute. Along the treemap there's a histogram showing the distribution of metric values over all Classes.

--- .class #id 

## Results

The shiny App shows the feasibility of the Analysis Pipeline. It can be used to do some exploratory Analysis on JUnit Source Code Metrics.

--- .class #id 

## Conclusion

Software Metrics are an unvaluable tool for building qualitative Software. The introduced data collection and processing pipeline has shown it's feasibility. Next steps could be to allow users to upload their MSE-Files that they collected on theri software to allow for Exploratory Analysis of any Software possible.

--- .class #id 

## Reference
[1] Software Metrics: 
https://en.wikipedia.org/wiki/Software_metric

[2] Maintainablity Index: 
http://blogs.msdn.com/b/codeanalysis/archive/2007/11/20/maintainability-index-range-and-meaning.aspx

[3] JUnit Source Code: 
http://junit.org/

[4] InFamix Java Parser Download: 
https://www.intooitus.com/node/85/download

[5] MSE File Format - Find some Info about MSE here: 
http://www.themoosebook.org/book/table-of-contents

[6] Software analytics With R - My Preliminary work created taking part in [7]
https://github.com/huberp/SoftwareAnalyticsWithR

[7] openHPI MOOC on Visual Software Analytics: 
https://open.hpi.de/courses/softwareanalytics2015

[8] Shiny App: 
https://huberp.shinyapps.io/VisualSoftwareAnalytics/
