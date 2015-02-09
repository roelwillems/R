# Basic three col table

```r
A <- c(1,2,3,4,5,6)
B <- c("yes","no","no","yes","yes","no")
C <- c("this is ok", "this is not","this is not","this is ok","this is ok", "this is not")
data <- data.frame(A, B, C)
```
## Result
|     A      |       B     |       C      |
|------------|-------------|--------------|
| 1          |     yes     | this is ok   |
| 2          |     no      | this is not  |
| 3          |     no      | this is not  |
| 4          |     yes     | this is ok   |
| 5          |     yes     | this is ok   |
| 6          |     no      | this is not  |
