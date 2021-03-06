

## Add the base numbers to a genome

In some cases it might be interesting to add a guide of the base numbering to 
the ideograms. The default function in karyoploteR to do that is 
**kpAddBaseNumbers**. It will add the base numbering below each chromosome in
the karyoplot.


```r
library(karyoploteR)

kp <- plotKaryotype()
kpAddBaseNumbers(kp)
```

![plot of chunk Figure1](figure/Figure1-1.png)

as with all other functions in karyoploteR it is possible to customize the 
appearance of the numbering mostly using standard graphics parameters. In 
addition, it is also possible to specify the distance between the tick marks 
and the size of the ticks. The color of the tick marks can be specified for all
of them using *col* or separately for major and minor ticks using the specific
parameters


```r
kp <- plotKaryotype(chromosomes="chr8", plot.type = 2)

kpAddBaseNumbers(kp, tick.dist = 10000000, tick.len = 10, tick.col="red", cex=1,
                 minor.tick.dist = 1000000, minor.tick.len = 5, minor.tick.col = "gray")
```

![plot of chunk Figure2](figure/Figure2-1.png)

## Add the cytoband names to an ideogram

In addition to the base numbering it is possible to add the cytoband names to
the ideogram. To do that we simply need a call to **kpAddCytobandLabels**.


```r
kp <- plotKaryotype(chromosomes="chr17")
kpAddCytobandLabels(kp)
```

![plot of chunk Figure3](figure/Figure3-1.png)

By default, it checks the size of the label and plots only those that fit inside
their cytoband. To force it to plot all labels even if they end up spilling or 
overlapping, set **force.all** to TRUE


```r
kp <- plotKaryotype(chromosomes="chr17")
kpAddCytobandLabels(kp, force.all = TRUE)
```

![plot of chunk Figure4](figure/Figure4-1.png)

Again, it is possible to customize the plotting with the standard graphical
parameters


```r
kp <- plotKaryotype(chromosomes="chr17")
kpAddCytobandLabels(kp, force.all = TRUE, srt=90, col="orange", cex=0.8)
```

![plot of chunk Figure5](figure/Figure5-1.png)
