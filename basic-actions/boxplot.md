# Boxplot


## Example data:
|      |       Goal           |	Variation.Name      | 	 Date	   |  Visitors  |	Conversions |	Conversion.Rate  |
| ---- | -------------------- | ------------------- | ---------- | ---------- | ----------- | ---------------- |
|   1  | Primary conversion    |	Control	            | 29/01/15   |	   70	    |     3       |	    4.285714     |
|   2  | Primary conversion    |	Control	            | 30/01/15	 |     99	    |     1       |     1.010101     |
|   3  | Primary conversion    |	Control             | 31/01/15	 |     49	    |     0       |   	0.000000     |
|   4  | Primary conversion    |	Control	            | 01/02/15	 |     48	    |     1       |   	2.083333     |
|   5	 | Primary conversion    |	Control	            | 02/02/15	 |     66	    |     1	      |     1.515152     |
|   6	 | Primary conversion    |	Control	            | 03/02/15	 |     66	    |     3       |   	4.545455     |
|   7	 | Primary conversion    |	Control	            | 04/02/15	 |     70	    |     2	      |     2.857143     |
|   8	 | Primary conversion    |	Control	            | 05/02/15	 |     68	    |     3       |    	4.411765     |
|   9	 | Primary conversion    |	Control	            | 06/02/15	 |     64	    |     1       |   	1.562500     |
|   10 | Primary conversion    |	Control	            | 07/02/15	 |     55	    |     2       |   	3.636364     |
|   11 | Primary conversion    |	Control	            | 08/02/15   |     52	    |     0	      |     0.000000     |
|   12 | Primary conversion    |	Control	            | 09/02/15	 |     10	    |     0       |   	0.000000     |
|   13 | Primary conversion    |	Variation 1	        | 29/01/15	 |     57	    |     0	      |     0.000000     |
|   14 | Primary conversion    |	Variation 1	        | 30/01/15	 |     79	    |     6       |   	7.594937     |
|   15 | Primary conversion    |	Variation 1	        | 31/01/15	 |     53	    |     1	      |     1.886792     |
|   16 | Primary conversion    |	Variation 1	        | 01/02/15	 |     51     |     0	      |     0.000000     |
|   17 | Primary conversion    | Variation 1	        | 02/02/15   |     77     |     2	      |     2.597403     |
|   18 | Primary conversion    | Variation 1	        | 03/02/15	 |     82     |     5	      |     6.097561     |
|   19 | Primary conversion    |	Variation 1	        | 04/02/15   |     75	    |     5	      |     6.666667     |
|   20 | Primary conversion    |	Variation 1	        | 05/02/15	 |     60	    |     0       |   	0.000000     |
|   21 | Primary conversion    |	Variation 1	        | 06/02/15	 |     59	    |     2       |   	3.389831     |
|   22 | Primary conversion    |	Variation 1	        | 07/02/15	 |     51	    |     5       |   	9.803922     |
|   23 | Primary conversion    |	Variation 1	        | 08/02/15	 |     48	    |     1	      |     2.083333     |
|   24 | Primary conversion	   | Variation 1	        | 09/02/15	 |      6	    |     0	      |     0.000000     |

## Splitting data based on the variation in different data frames
This is optional. Although in my experience working with data frames makes it more easy to alter / controle the final output.

__Building the Control data.frame__
```r
control <- data[(data$Variation.Name=="Control"),]
```

__Building the Variation data.frame
```r
variation <- data[(data$Variation.Name=="Variation 1"),]
```

## Drawing the boxplot based on both data.frames
To draw the final boxplot we will use the [boxplot()][1] function.

```r
boxplot(control$Conversion.Rate, variation$Conversion.Rate, horizontal=TRUE, col=(c("lightgrey","darkgrey")),main="Site speed test", xlab="Conversion rate", names = c("Control","Variation"))
```

Using _control$Conversion.Rate_ and varation$Conversion.Rate we draw the colum Conversion.Rate from both data.frames.

- Horizontal=TRUE makes sure that the boxplot is drawn horizonally instead of vertically. 
- The additional of _col=(c("lightgrey","darkgrey"))_ determines the color of the boxplot body. 
- Main, xlab and names the legenda is added.

## Output
![Boxplot example](https://github.com/roelwillems/R/blob/master/images/boxplot-example.png)

```r
> t.test(control$Conversions, variation$Conversions)

	Welch Two Sample t-test

data:  control$Conversions and variation$Conversions
t = -1.1043, df = 16.132, p-value = 0.2857
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -2.4319820  0.7653154
sample estimates:
mean of x mean of y 
 1.416667  2.250000 
```

[1]: http://statmethods.net/graphs/boxplot.html
