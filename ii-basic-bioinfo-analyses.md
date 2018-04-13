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

0.** **[**Background Introduction \(PPT\)**](https://www.jianguoyun.com/p/DTwA_GEQ0NLuBRjA9UY)

1. **Mapping, Annotation **and** QC**
2. **Differential Expression Analysis**
3. **Clustering **- Visualize the data
4. **Normalization** 
5. **Imputation**
6. **Control Data**

#####  {#rnaseq}

##### Shared Data: {#rnaseq}

```bash
chown -R root:share *  # add a share group, and add all shared DIRs and FILEs to this group

chmod -R 775 * # make all DIRs writable and executable by "share" group

# The permission for FILEs:

chmod  444 *.fastq # all the raw data are read-only for all users

chmod 664 *  # normal files

chmod 775 REAMDE Metatable.txt # highlight README files with color by making them executable

chmod 775 shared_scripts/* #  scripts need to be executable (better to be 755 or even 555)
```



