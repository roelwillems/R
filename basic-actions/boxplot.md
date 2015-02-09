# Boxplot


## Example data:
|      |       Goal           |	Variation.Name      | 	 Date	   |  Visitors  |	Conversions |	Conversion.Rate  |
| ---- | -------------------- | ------------------- | ---------- | ---------- | ----------- | ---------------- |
|   1  | Polis bevestiging    |	Control	            | 29/01/15   |	   70	    |     3       |	    4.285714     |
|   2  | Polis bevestiging    |	Control	            | 30/01/15	 |     99	    |     1       |     1.010101     |
|   3  | Polis bevestiging    |	Control             | 31/01/15	 |     49	    |     0       |   	0.000000     |
|   4  | Polis bevestiging    |	Control	            | 01/02/15	 |     48	    |     1       |   	2.083333     |
|   5	 | Polis bevestiging    |	Control	            | 02/02/15	 |     66	    |     1	      |     1.515152     |
|   6	 | Polis bevestiging    |	Control	            | 03/02/15	 |     66	    |     3       |   	4.545455     |
|   7	 | Polis bevestiging    |	Control	            | 04/02/15	 |     70	    |     2	      |     2.857143     |
|   8	 | Polis bevestiging    |	Control	            | 05/02/15	 |     68	    |     3       |    	4.411765     |
|   9	 | Polis bevestiging    |	Control	            | 06/02/15	 |     64	    |     1       |   	1.562500     |
|   10 | Polis bevestiging    |	Control	            | 07/02/15	 |     55	    |     2       |   	3.636364     |
|   11 | Polis bevestiging    |	Control	            | 08/02/15   |     52	    |     0	      |     0.000000     |
|   12 | Polis bevestiging    |	Control	            | 09/02/15	 |     10	    |     0       |   	0.000000     |
|   13 | Polis bevestiging    |	Variation 1	        | 29/01/15	 |     57	    |     0	      |     0.000000     |
|   14 | Polis bevestiging    |	Variation 1	        | 30/01/15	 |     79	    |     6       |   	7.594937     |
|   15 | Polis bevestiging    |	Variation 1	        | 31/01/15	 |     53	    |     1	      |     1.886792     |
|   16 | Polis bevestiging    |	Variation 1	        | 01/02/15	 |     51     |     0	      |     0.000000     |
|   17 | Polis bevestiging    | Variation 1	        | 02/02/15   |     77     |     2	      |     2.597403     |
|   18 | Polis bevestiging    | Variation 1	        | 03/02/15	 |     82     |     5	      |     6.097561     |
|   19 | Polis bevestiging    |	Variation 1	        | 04/02/15   |     75	    |     5	      |     6.666667     |
|   20 | Polis bevestiging    |	Variation 1	        | 05/02/15	 |     60	    |     0       |   	0.000000     |
|   21 | Polis bevestiging    |	Variation 1	        | 06/02/15	 |     59	    |     2       |   	3.389831     |
|   22 | Polis bevestiging    |	Variation 1	        | 07/02/15	 |     51	    |     5       |   	9.803922     |
|   23 | Polis bevestiging    |	Variation 1	        | 08/02/15	 |     48	    |     1	      |     2.083333     |
|   24 | Polis bevestiging	  | Variation 1	        | 09/02/15	 |      6	    |     0	      |     0.000000     |

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
![Boxplot example](images/boxplot-example.png)

[1]: http://statmethods.net/graphs/boxplot.html
