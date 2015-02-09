# Vectors
A vector is a sequence of data elements of the same basic type. Members in a vector are officially called components. Nevertheless, we will just call them members in this site.

## Example

### Numeric values (e.g. 2, 3 and 5)
```r
> c(2, 3, 5) 
[1] 2 3 5
```
### Logical values
```r
> c(TRUE, FALSE, TRUE, FALSE, FALSE) 
[1]  TRUE FALSE  TRUE FALSE FALSE
```

### Character strings.
```r
> c("aa", "bb", "cc", "dd", "ee") 
[1] "aa" "bb" "cc" "dd" "ee"
```

### Number of components in a vector is given by the length function.
```r
> length(c("aa", "bb", "cc", "dd", "ee")) 
[1] 5
```
