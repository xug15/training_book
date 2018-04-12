# **Mapping, Annotation **and** QC**

---

### 1\) Understand your data

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
vim .bashrc # see my example in /home/john/.bashrc (and /home/john/shortcuts)
mkdir github

mkdir -p ~/projects/exRNA
cd ~/projects/exRNA

alias mkpr="mkdir -p {data/mapped,scripts,analysis}"  # you can put this in your ~/.bashrc
mkpr
```

### 3\) Get the software ready

[Install bioinformatics software in Linux \(centos\)](https://lulab.gitbooks.io/bioinfo-training-2018/content/software-installation-on-cnode.html)

### 4\) Mapping, Annotation and QC

学习并完成这里面的作业：[ ](https://youngleebbs.gitbooks.io/bioinformatics-training-program/content/exrna-seq-analysis/1preprocessing-mapping-and-qc.html)

* [Additional Tutorial](https://youngleebbs.gitbooks.io/bioinformatics-training-program/content/exrna-seq-analysis/1preprocessing-mapping-and-qc.html) 
* [Teaching PPT](https://www.jianguoyun.com/p/DTwA_GEQ0NLuBRjA9UY): II. Basic Bioinfo Analyses: 0. Introduction to exRNA-seq; 1. Mapping, Annotation and QC
* [Teaching Video](http://list.youku.com/albumlist/show/id_51618375.html): Week V. 0.Introduction of exRNA-seq; 1.Mapping, Annotation and QC

**Protocol:**

cd ~/projects/exRNA/hcc\_examples/

| Step | Input | Tool/script | Output | Working directory |
| :--- | :--- | :--- | :--- | :--- |
| 1.Preprocessing | 00.rawdata/\*.fastq | - | 02.rRNA/sampleID/sampleID.no\_rRNA.fastq |  |
| 1.1 fastqc | 00.rawdata/\*.fastq | fastqc | 00.rawdata/\*\_fastqc.html | check raw reads' quality |
| 1.2 Remove 3' adapter and trim reads | 00.rawdata/\*.fastq | cutadapt | 01.cutAdapter/sampleID/sampleID.trimmed.cutAdapt3.fastq | trim low quality ends \(plus a hard cutoff: 50nt\) |
| 1.3 2nd fastqc | 01.cutAdapter/sampleID/sampleID.trimmed.cutAdapt3.fastq | fastqc | 01.cutAdapter/sampleID/sampleID.trimmed.cutAdapt3\_fastqc.html | make sure the low quality reads have been removed and/or trimmed |
| 1.4 Remove ribosomal RNA | 01.cutAdapter/sampleID/sampleID.trimmed.cutAdapt3.fastq | bowtie2 | 02.rRNA/sampleID/sampleID.rRNA.sam 02.rRNA/sampleID/sampleID.no\_rRNA.fastq | - |
| 2.Mapping | 02.rRNA/sampleID/sampleID.no\_rRNA.fastq | bowtie2 | 03.mapping/sampleID/01.miRNA/sampleID.miRNA.sam 03.mapping/sampleID/01.miRNA/sampleID.no\_miRNA.fastq --&gt;  03.mapping/sampleID/02.piRNA/sampleID.piRNA.sam 03.mapping/sampleID/02.piRNA/sampleID.no\_piRNA.fastq --&gt; ... | map to different RNA annotations step by step |



