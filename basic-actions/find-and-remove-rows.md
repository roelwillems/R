#Find values and remove the corresponding rows if they meet the logical condition:

## Example data:
|     A      |       B     |       C      |
|------------|-------------|--------------|
| 1          |     yes     | this is ok   |
| 2          |     no      | this is not  |
| 3          |     no      | this is not  |
| 4          |     yes     | this is ok   |
| 5          |     yes     | this is ok   |
| 6          |     no      | this is not  |


## Check to see if the value is present
```r
data[!(data$B=="no"),]
```
This will check all rows where colum B contain "no".

### To check against multiple colums
```r
data[!(data$B=="no" & d$C=="this is not"),]
```

This will check all rows where for colum B are equal to "no" and C are equal to "this is not".

## Writing the cleaned data to the dataset
```r
data <- data[!(data$B=="no" & d$C=="this is not"),]
```

## Result:
|     A      |       B     |       C      |
|------------|-------------|--------------|
| 1          |     yes     | this is ok   |
| 2          |     yes     | this is ok   |
| 3          |     yes     | this is ok   |

