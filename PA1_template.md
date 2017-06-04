# Reproducible Research: Peer Assessment 1

## Loading and preprocessing the data
Unzip and load data and do necessary/helpful transformations.

```r
unzip("activity.zip")
activity <- read.csv("activity.csv")
```

## What is mean total number of steps taken per day?
Calculate steps per day

```r
stepsPerDay <- tapply(activity$steps, activity$date, sum, na.rm = T)
b <- seq(0, 22000, length.out = 12)
hist(stepsPerDay, breaks = b, main = "Number of days with amount of Steps", ylab = "# of days", xlab = "# of Steps", axes = F)
axis(2)
axis(1, at = b, labels = b)
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png)<!-- -->


Overall, the mean of steps per day was 9354, while the median of steps per day is 1.0395\times 10^{4}

## What is the average daily activity pattern?

```r
t <- tapply(activity$steps, activity$interval, mean, na.rm = T)
plot(t, type = "l", main = "Activity seems to be the highest between 8 and 9 in the morning", ylab = "Avg # of steps", xlab = "Time interval", axes = F)
axis(2)
axis(1, at = 1:length(t), labels = names(t))
```

![](PA1_template_files/figure-html/unnamed-chunk-4-1.png)<!-- -->


## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?



