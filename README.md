---
title: "DDP Week 3 Assignment"
author: "sarah"
date: 'friday, oct 25 2024'
output: ioslides_presentation
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = FALSE)
```

## Gas Mileage

Using `mtcars`, plotting the relationship of various factors to gas mileage (`mpg`).

Plotting weight (`wt`) vs. mileage (`mpg`) spatially along the x/y axes. Then visualising the number of cylinders (`cyl`) as colors and the amount of horsepower (`hp`) as the size of an individual point in the plot.

## Plotly 

```{r plot, echo=FALSE}
suppressPackageStartupMessages(library(plotly))
plot_ly(data = mtcars, x = ~wt, y = ~mpg, 
        color = ~as.factor(cyl), size = ~hp,
        text = ~paste("Weight: ", wt, '<br><hr>MPG:', mpg),
        type = "scatter", mode = "markers") %>%
  layout(title = "Car Mileage")
``` 
