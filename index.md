---
title       : Body Mass Index
subtitle    : Develpoing Data products - Shiny
author      : ltl
job         : student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]     # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Intruduction

Body Mass Index (BMI) is a simple index of weight-for-height that is commonly used to classify underweight, overweight and obesity in adults. It is defined as the weight in kilograms divided by the square of the height in metres (kg/m2).

### classification standard

- BMI <18.5 : Underweight
- BMI [18.5-25) : Optimal weight
- BMI [25-30) : Overweight
- BMI >=30 : Obese

---

## The website of shiny

![shiny](D:/study/coursera/9_Developing Data Products/project/BMI_slidify/shiny.png)


[http://litenglong1988.shinyapps.io/BodyMassIndex](https://litenglong1988.shinyapps.io/BodyMassIndex)

---

## How is it calculated?

BMI Difinition:

$$BMI=\frac{Weight(kg)}{Height(m)^{2}}$$

code example:
assume that my weight is 58kg, height is 168cm, calculate the BMI


```r
weight <- 58
height <- 168
bmi <- Weight/(Height/100)^2
```

```
## Error: object 'Weight' not found
```

```r
bmi
```

```
## Error: object 'bmi' not found
```

---

## more shiny code

**what is in server.r?**

we must judge people's body body fatness as follow:


```r
bmifunc <- function(height, weight){
    bmi <- weight/(height/100)^2
    if(bmi < 18.5) "underweight"
    else if(bmi >= 18.5 & bmi < 25) "optimal weight"
    else if(bmi >= 25 & bmi < 30) "overweight"
    else "obese"
}
bmifunc(height, weight)
```

```
## [1] "optimal weight"
```

