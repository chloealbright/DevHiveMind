---
title: |-
  | ![](logo.jpg){width=6in} \vspace{0.2in} 
  `r format(params$term)` Grades Report
   \vspace{0.1in}
subtitle: ""
author: |-
  Dr. Devrim Ozdemir
   \vspace{1in} 
date: Last compiled on `r format(Sys.time(), '%B %d, %Y')`
output: pdf_document
params: 
term: Fall 2020
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(
    echo = FALSE,
    message = FALSE,
    warning = FALSE
)
library(tidyverse)
library(kableExtra)

Grades <- read_csv("DataFolder/Fall_2020_Grades.csv")

```

\newpage
# Introduction

The grade distribution presented for each exam and each student in  the table below.




Creating a Functional Title Page in R Markdown
https://www.linkedin.com/pulse/creating-functional-title-page-r-markdown-devrim-ozdemir?utm_source=share&utm_medium=member_android&utm_campaign=share_via