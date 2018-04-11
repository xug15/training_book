# **Mapping, Annotation **and** QC**

---

### 1\) Understand your data

**exRNA-seq:**

* Sequencing machine ?
* Single-strand V.S. Paired-end ?
* Strand specific ?
* Size selection ?
* Poly-A enriched or total \(ribosome removed\) ?
* Cellular localization ?

### 2\) Organize your data

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
vim .bashrc # see my example in /home/john/.bashrc (and shortcuts)
mkdir github

mkdir -p ~/projects/exRNA
cd ~/projects/exRNA
mkpr
```

> see previous introduction on home to [make you own mkpr](/ii-basic-bioinfo-analyses.md#mkpr)

### 3\) Get the software ready

[Install bioinformatics software in Linux \(centos\)](https://lulab.gitbooks.io/bioinfo-training-2018/content/software-installation-on-cnode.html)

### 4\) Mapping, Annotate and QC

学习并完成这里面的作业：[ Additional Tutorial](https://youngleebbs.gitbooks.io/bioinformatics-training-program/content/exrna-seq-analysis/1preprocessing-mapping-and-qc.html)

