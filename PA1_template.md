# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

The first thing to do is to import the library that we'll need in this analysis.

```r
library(ggplot2)
```


We can now start to open the csv file, convert it to a data.frame and preprocess the data in order to have a tidy and useful dataset.

```r
# open the dataset
dataset <- read.csv("./activity.csv")
# convertions
dataset$date <- as.Date(dataset$date)
dataset$steps <- as.numeric(as.character(dataset$steps))
dataset$interval <- as.numeric(as.character(dataset$interval))
head(dataset)
```

```
##   steps       date interval
## 1    NA 2012-10-01        0
## 2    NA 2012-10-01        5
## 3    NA 2012-10-01       10
## 4    NA 2012-10-01       15
## 5    NA 2012-10-01       20
## 6    NA 2012-10-01       25
```

```r
# preprocessing
steps_sum <- as.data.frame(tapply(dataset$steps, dataset$date, sum, na.rm = TRUE))
colnames(steps_sum)[1] <- "steps"
```

We now have a tidy and simple dataset to analize:

```r
str(steps_sum)
```

```
## 'data.frame':	61 obs. of  1 variable:
##  $ steps: num [1:61(1d)] 0 126 11352 12116 13294 ...
##   ..- attr(*, "dimnames")=List of 1
##   .. ..$ : chr  "2012-10-01" "2012-10-02" "2012-10-03" "2012-10-04" ...
```

```r
head(steps_sum)
```

```
##            steps
## 2012-10-01     0
## 2012-10-02   126
## 2012-10-03 11352
## 2012-10-04 12116
## 2012-10-05 13294
## 2012-10-06 15420
```



## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
