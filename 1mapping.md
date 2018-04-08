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

**Shared Data dir:**

SHARE="/1PB/Lulab\_b/shared"

* $SHARE/shared\_scripts/ \#executable tools
* $SHARE/genomes/hg38
  * fasta/ \#sequences of reference genome 
  * gff/   \#annotation of reference genome \(gencode, hg38\)
* $SHARE/projects/exRNA/
  * data \#sequencing raw data, usually fastq files
    * fastq\_hcc
    * fastq\_pnas2015
    * fastq\_sr2017

**Make your own project dir:**

```bash
mkdir -p ~/projects/exRNA
cd ~/projects/exRNA
mkpr
ln -s $SHARE/projects/exRNA/data .
ln -s $SHARE/genomes/hg38 .
ln -s $SHARE/shared_scripts .
```

### 3\) Get the software ready

[Install bioinformatics software in Linux \(centos\)](https://lulab.gitbooks.io/bioinfo-training-2018/content/software-installation-on-cnode.html)

### 4\) Mapping, Annotate and QC

### 



