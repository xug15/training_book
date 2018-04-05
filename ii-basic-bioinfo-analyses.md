# II. Basic Bioinfo Analyses

Case Studies

---

## 1\) Work with a computing server remotely {#1}

1. [ssh](/1setup.md#ssh) and [ssh keys](/2linux.md#ssh-key)
2. [nohub, screen or tmux](/2linux.md#nohup)

> **More Reading**
>
> &lt;&lt;Bioinformatics Data Skills&gt;&gt;
>
> 4\) Working with Remote Machines

## 2\) Initiate a project

```bash
alias mkpr="mkdir -p {data/mapped,scripts,analysis}"  # you can put this in your ~/.bashrc
mkpr
```

## 3\) Bioinformatics data

## 4\) Let's start a real case

### Find novel exRNA biomarkers for cancer diagnosis

---

#### Background

##### Type of RNA-seq {#rnaseq}

* **Default:** \(whole cell poly-A\) RNA-seq  \(&gt;200nt\)

* **Other types:**

  * small RNA-seq  \(&lt;50nt\)
  * total RNA-seq \(ribosome removed\) \(&gt;200nt\)
  * nonpolyA RNA-seq \(ribosome removed\) \(&gt;200nt\)

* [**Different cell localizations**](/6control.md#local)**:**

  * nuc. \(total\) 
  * chromosome \(total\) 
  * cyto. \(poly-A\) 

* **Single cell RNA-seq**

* **exRNA-seq**

  * cell free/MV/exosome/RNP
  * small/long

#####  {#rnaseq}

##### [More](https://www.jianguoyun.com/p/DTwA_GEQ0NLuBRjA9UY#dir=%2FII.%20Basic%20Bioinfo%20Analyses::mode=0) {#rnaseq}



