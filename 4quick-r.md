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

## 

## 2）Examples

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



### 3）更多阅读和练习

---

阅读和练习[Quick R](https://www.statmethods.net/) 如下章节 :

> Learning R  
> R Interface  
> Data Input  
> Statistics
>
> ...



