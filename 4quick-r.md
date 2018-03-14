# 4.R

How to make professional and beautiful plots

---

> **Tips:**
>
> Do things with multiple ways
>
> Efficient Writing: Bash &gt; R &gt; Perl/Python &gt; Excel &gt; C++

## Examples

#### Example I. t test

---

sh\# R

```R
  x<-read.table("foo1")
  y<-read.table("foo2")
  mean(x)
  mean(y)
  t.test(x,y,alternative=c("greater") )
```

or write these into a file, script.R, then run  
`R CMD BATCH script.R`

