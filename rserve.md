---
title: "Anomaly Detection in Time Series Data"
author: "Your Name"
date: "`r format(Sys.Date(), '%B %d, %Y')`"
output: html_document
---

## Overview

This document presents an R script for detecting anomalies in time series data. The script is designed to be integrated into a Tableau environment.

## Libraries

```{r, message=FALSE}
# Load necessary libraries
library(tidyverse) # tidyverse includes dplyr
library(anomalize)
library(tibbletime)

## Anomaly detection function
# See rserve-anomalize in root for function description and details

## Example Usage Within Tableau Desktop

The anomaly detection function can be integrated into Tableau Desktop using the `SCRIPT_BOOL` function. This function allows Tableau to run R scripts and receive a boolean output.

# Integrating with `SCRIPT_BOOL`

To use the R script in Tableau, wrap it in `SCRIPT_BOOL` as follows:

```text
SCRIPT_BOOL("
  source('path_to_your_R_script.R')
  detect_anomalies(.arg1, .arg2)
", ATTR([Day]), SUM([Impressions]))
