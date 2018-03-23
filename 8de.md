# Differential Expression

[Normalizing single-cell RNA sequencing data: challenges and opportunities, _Nature Methods_, 2017](https://www.ncbi.nlm.nih.gov/pubmed/28504683)

### Problems and issues

---

* Sparsity of data and technical noise \("batch effects"\) --&gt; will mask the signal of interest

**Causes:**

![](/assets/noise.png)

## Computational Methods

---

**Assumption** for most normalization and differential expression analysis tools:

_The expression levels of most genes are similar, i.e., not differentially expressed._

**Recommendation for bulk RNA-seq**

* **RPM**: Read counts Per Million of total mapped reads; alternatives: RPKM, TPM
* **DEseq**: defines **scaling factor **\(also known as **size factor**\) estimates based on a pseudoreference sample, which is built with the geometric mean of gene counts across all cells \(samples\).
* [**TMM**](https://www.ncbi.nlm.nih.gov/pubmed/20196867)** **\(**EdgeR**\): trimmed mean of _M_ values

![](/assets/M.png)

**Recommendation for single cell RNA-seq \(and exRNA-seq\)**

1. **scran: **
   1. pools multiple cells \(samples\) in order to estimate cell-specific size factors in the **presence of zero inflation** and **unbalanced differential expression** of genes across groups of cells;** **
   2. **precluster** \(using e.g. rank-based clustering\) the cells into smaller, more homogeneous sets 
2. SCnorm
3. Census

If considering spike-ins:

1. SAMstrt
2. GRM

**Performance**

![](/img/performance.png)

### **Spike-in**

---

**RNA content \(total amount and species\) varies**

![](/img/RNA content.png)

**for mRNAs:**

* 92 ERCC molecules
* 8 mRNAs
* whole transcriptome HeLa RNAs

**for sRNAs:**

* 52\(?\) sRNA sequences

**Caveat:**

Typically only half of the spike-in were detected.

