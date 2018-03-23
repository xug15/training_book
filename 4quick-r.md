# 4.R

How to make professional and beautiful plots

---

> **Tips:**
>
> Do things with multiple ways
>
> Efficient Writing: Bash &gt; R &gt; Perl/Python &gt; Excel &gt; C,C++

## 

## 1）install R

---

```
yum -y install epel-release
yum -y install R
```

* How to quit?

`q()`

* How to get help?

`?t.test`

## 2）Examples

#### Example I. t test

---

sh\# R

```R
x<-read.table("foo1")
y<-read.table("foo2")
t.test(x,y,alternative=c("less") )

x=x[,1]
y=y[,1]
t.test(x,y,altrenative=c("less"),paired=TRUE)
```

or write these into a file, script.R, then run  
`R CMD BATCH script.R`

#### Example II. heatmap

---

```R
require("gplots")
# open an image file
png("sample_heatmap.R.png",width=2048,height=2048)
m <- matrix(runif(n=30*30, min=-1.0, max=1.0), ncol=30)
mn <- -1
mx <- 1
n <- 98        # the color steps, 98 color levels.
density.info <- "none"    # whether to display density in the key
bias <- 1    # parameter for colorRampPalette. 1 is what I used
mc <- matrix(as.character(round(m, 2)), ncol=dim(m)[2])     # the note on the matrix
breaks <- seq(mn, mx, (mx-mn)/(n))
cr <- colorRampPalette(colors = c("#2927FF","#FFFFFF","#DF5C5C"), bias=bias)
heatmap.2(m, col = cr(n), breaks=breaks, trace="none", cellnote=mc, notecol="black",
notecex=1.800000, keysize=0.500000, density.info=density.info, margins=c(27.000000,27.000000),
cexRow=2.200000, cexCol=2.200000)
dev.off()
```

### 3）更多阅读和练习

---

* **Basic Reading for Beginners **

阅读和练习[Quick R](https://www.statmethods.net/) 如下章节 :

> Learning R  
> R Interface  
> Data Input  
> Statistics

* **Reading for Advanced Readers **

a\) 阅读和练习[Quick R](https://www.statmethods.net/) 如下章节 :

> Learning R  
> R Interface  
> Data Input  
> Statistics
>
> ...

b\) Bioinformatics Data Skills

> 8\) A Rapid Introduction to the R Language

c\) [**More Examples at Github**](https://www.gitbook.com/book/lulab/bioinfo-training/edit#)

d\) [**Additional Tutorial**](https://youngleebbs.gitbooks.io/bash-and-r-scripts/content/chapter1.html)

