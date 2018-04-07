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

* /shared\_scripts/ \#executable tools
* /genomes/hg38
  * fasta/ \#sequences of reference genome 
  * gff/   \#annotation of reference genome (gencode, hg38)
* /projects/exRNA/
  * data \#sequencing raw data, usually fastq files
    * fastq_hcc
    * fastq_pnas2015
    * fastq_sr2017


**Make your own project dir:**

```bash
mkdir -p ~/projects/exRNA
cd ~/projects/exRNA
mkpr
ln -s /projects/exRNA/data .
ln -s /genomes/hg38 .
ln -s /shared_scripts .
```

### 3\) Get the software ready

#### Install bioinformatics software in Linux \(centos\)

```
mkdir /download
```

```bash
cd /download
wget -c http://www.cpan.org/src/5.0/perl-5.26.1.tar.gz
tar -xvzf perl-5.26.1.tar.gz
cd /download/perl-5.26.1
sh Configure -de
make
make test  # you can skip this if you are confident
make install
```

### 4\) Map

### 5\) QC

### 

### 6\) Annotate



