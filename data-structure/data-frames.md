# Data frames

The weights, prices, and types data structures are all deeply tied together, if you think about it. If you add a new weight sample, you need to remember to add a new price and type, or risk everything falling out of sync. To avoid trouble, it would be nice if we could tie all these variables together in a single data structure. Fortunately, R has a structure for just this purpose: the data frame. You can think of a data frame as something akin to a database table or an Excel spreadsheet. It has a specific number of columns, each of which is expected to contain values of a particular type. It also has an indeterminate number of rows - sets of related values for each column.

Our vectors with treasure chest data are perfect candidates for conversion to a data frame. And it's easy to do. Call the *data.frame* function, and pass weights, prices, and types as the arguments. Assign the result to the treasure variable:

```r
 treasure <- data.frame(weights, prices, types)
```

Now, try printing treasure to see its contents:

```r
print(treasure)
```

|         | weights |  prices | types   |
|---------|---------|---------|---------|
|    1    |     300 |   9000  | gold    |
|    2    |     200 |   5000  | silver  |
|    3    |     100 |  12000  | gems    |
|    4    |     250 |   7500  | gold    |
|    5    |     150 |  18000  | gems    |

There's your new data frame, neatly organized into rows, with column names (derived from the variable names) across the top.
