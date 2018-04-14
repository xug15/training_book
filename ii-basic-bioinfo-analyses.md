# Introduction of Part II. Basic Bioinfo Analyses

Case Study

---

## 1\) Work with a computing server remotely {#1}

1. [ssh](/1setup.md#ssh) and [ssh keys](/2linux.md#ssh-key)
2. [nohub, screen or tmux](/2linux.md#nohup)

> **More Reading**
>
> &lt;&lt;Bioinformatics Data Skills&gt;&gt;
>
> 4\) Working with Remote Machines

## 2\) Let's start a real case

### -- identify novel exRNA biomarkers for cancer diagnosis

---

Outline:  
1. **Mapping, Annotation **and** QC**  
2. **Differential Expression Analysis**  
3. **Clustering **- Visualize the data  
4. **Normalization**  
5. **Imputation**  
6. **Control Data**  
7. **Extension**

#### a\) Background Introduction

* [PPT](https://www.jianguoyun.com/p/DTwA_GEQ0NLuBRjA9UY): II. Basic Bioinfo Analyses/0. Introduction of exRNA-seq.pdf \(view on-line only, not downloadable\)
* [Teaching Video](http://list.youku.com/albumlist/show/id_51618375.html): Week V - Part II. 0. Intr to exRNA-seq.mov

#### b\) Understand your data

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

**So what RNA-seq we are mapping and analyzing?**

* Sequencing machine ?
* Single-strand V.S. Paired-end ?
* Strand specific ?
* Size selection ?
* Poly-A enriched or total \(ribosome removed\) ?
* Cellular localization ?

#### c\) Organize your data

[**Data format**](https://genome.ucsc.edu/FAQ/FAQformat.html)**:**

* fasta
* fastaq
* gff/gtf
* bam
* bed
* bigwig

**Shared dirs/data:**

```
cd  #go to my home
ln -s /BioII/lulab_b/shared/genomes  .   #shared reference genome sequeunces and annotations
ln -s /BioII/lulab_b/shared/shared_scripts  .  #shared scripts in Lu Lab
ln -s /BioII/lulab_b/shared/projects/exRNA  shared_exRNA_projects   #shared projects' files
```

* ~/genomes/human\_hg38
  * sequences/ \#sequences of reference genome \(fasta format\)
  * index/ \# indexed genome sequences
  * gtf/   \#annotation of reference genome 

**Make your own project dir:**

```bash
cd # go to my home
vim .bashrc # see my example in /home/john/.bashrc (and /home/john/shortcuts)
mkdir github

mkdir -p ~/projects/exRNA
cd ~/projects/exRNA

alias mkpr="mkdir -p {data/mapped,scripts,analysis}"  # you can put this in your ~/.bashrc
mkpr
```

#### d\) Get the software ready

[Install bioinformatics software in Linux \(centos\)](https://github.com/lulab/training/wiki/cnode)

