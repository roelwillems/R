# Basic three col table

```r
A <- c("yes","no","no","yes","yes","no")
B <- c("this is ok", "this is not","this is not","this is ok","this is ok", "this is not")
data <- data.frame(A, B)
```
## Result
|            |       A     |       B      |
|------------|-------------|--------------|
| 1          |     yes     | this is ok   |
| 2          |     no      | this is not  |
| 3          |     no      | this is not  |
| 4          |     yes     | this is ok   |
| 5          |     yes     | this is ok   |
| 6          |     no      | this is not  |
