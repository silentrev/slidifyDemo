---
title       : Predict the temperature of my apartment
subtitle    : My course project for Developing data products
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
github:
 user: silentrev
 repo: slidifyDemo
---

## Apartment and logged temperature 

* My apartment is located in a building constructed in the 30s 
* The building is poorly maintained and located in an open area close to the sea
* It is therefore quite exposed to the elements and I can notice a difference in indoor temperature depending on the weather
* About 18 months ago I installed a temperature logger in my apartment. This device records the indoor temperature every hour.


--- .class #id 

## Weather data and regression model
* I later paired the logged temperatures with weather data from a nearby weather station 
* This data set was used to create a linear regression model that can predict the indoor temperature of my apartment.
* The following weather variables was used as regressors: 
    - The outdoor temperature
    - The windspeed in m/s
    - The solar irradiation, daily average global beam   
    
* The model is obviously not very precise but can still give a picture of the climate in the apartment.

---

## Linear regression model example

Using the lienar regression model to calculate the indoor temperature

```r
wind <- 8 # Set Windspeed
temp <- 5 # Set outdoor temperature
sun <- 100 # Set global beam

indoorTemp = (21.21 + temp*0.013
            -((21-temp)*wind*wind*0.000294) 
            + sun*0.012)

indoorTemp <- round(indoorTemp,1)
```

With the weather parameters stated as above, the predicted temperature is 22.2 degrees celcius.

---
## How to use the shiny app
- The app is easy to use. Change the weather parameters with the sliders to the left.
- You can choose to view the predicted temperature in fahrenheit or celcius.
- You will also find a short guide explaining the weather parameters.
