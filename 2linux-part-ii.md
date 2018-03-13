# 2. Linux

How to work with command lines



### Linux - Part II. 上机任务

---

#### 1. 了解基因组注释文件 \(gff/gtf\)

**1.1 了解gff和gtf文件格式**


[Reference link](http://www.genome.ucsc.edu/FAQ/FAQformat.html) ：*http://www.genome.ucsc.edu/FAQ/FAQformat.html
*

**1.2 下载yeast的基因组注释文件**

**1.2.1** 先创建一个自己的文件夹

```
mkdir my_folder
```


**1.2.2** 下载

1） 下载方法1： 可以从terminal下载：

```
wget http://www.ncrnalab.org/lulab/public/1.gtf.gz

```


2） 下载方法2： yeast基因组注释文件可以从浏览器下载：

[Download link](https://www.jianguoyun.com/p/DTCJc-gQ0NLuBRj9kQ4#dir=%2F2016%2F%E7%94%9F%E7%89%A9%E4%BF%A1%E6%81%AF%E5%AD%A6%E5%AF%BC%E8%AE%BA%2F%E4%B8%8A%E6%9C%BA%E6%96%87%E4%BB%B6%2F3.Genomics%2FYeast%20Genome%20Annotation::mode=0)



3） 下载方法3：
该文件在"虚拟机"中已经下载好，位置在/home/cs/Bioinfo_Lab/0.Linux/myfolder下，文件名为  Sa*.gtf.gz
可以考到自己目录下：
```
cp /home/cs/Bioinfo_Lab/0.Linux/*.gtf.gz  .
```


>**Note:**
> 星字符：* 可以代表任何字符，称为wildcard。



**1.2.3** 解压缩

首先将*.gtf.gz放到自己创建的目录下（可以使用cp或者mv命令），
然后解压缩该文件：

```bash
gunzip *.gtf.gz
```


>** Tips **
>
> **1) 命令cp、文件“./*.gtf.gz”、目录“my_folder/”之间均存在空格。**
>
> **2) 在Linux命令行中， "." 可代表当前目录，".."可代表上一层目录。**
> 
> **3) tab键可以实现命令名及文件名的自动补全。**





**1.3 统计所下载gff/gtf文件的大小，行数和exon数目**

命令示范：

```bash
man ls
ls -al *.gtf
wc -l *.gtf
cut -f 3 *.gtf | sort | uniq -c
```

#### 2. 学会使用一个文本编辑器\(vi, nano, emacs\)编辑新的文件

写一个可执行文件，寻找长度最长的3个exon, 汇报其长度。

命令示范：

```vi run.sh```

rush.sh的文件内容：

```
#!/bin/bash   
grep exon *.gtf | awk '{print $5-$4+1}' | sort -n | tail -3
```
（第一行语句一般用来声明这个脚本使用的shell名称，“#”后的语句可作为批注，在执行时会被忽略）

关闭vi编辑器，返回命令行后键入：
```
chmod +x run.sh
./run.sh
```

>**Note**:
>
>  **vi编辑器的使用方法详见附录**。




