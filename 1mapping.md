# **Mapping, Annotation **and** QC**

---

### 1. Understand your data

**exRNA-seq:**

* Sequencing machine ?
* Single-strand V.S. Paired-end ?
* Strand specific ?
* Size selection ?
* Poly-A enriched or total \(ribosome removed\) ?
* Cellular localization ?

### 2. Organize your data

[**Data format**](https://genome.ucsc.edu/FAQ/FAQformat.html)**:**

* fasta
* fastaq
* gff/gtf
* bam
* bed

**Data dir:**

* /projects/exRNA/
  * seq/      #sequencing raw data, usually fastq files
  * fasta/    #sequences of reference genome 
  * gff/      #annotation of reference genome (gencode, hg38)
  * bin/      #executable tools





### 3. Get the software ready

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

### 4. Map

### 5. QC

### 

### 6. Annotate



