# 2. Linux

### 上机任务

**Linux基础和基因组注释文件解读**

---

#### 1. 了解基因组注释文件 \(gff/gtf\)

**1.1 了解gff和gtf文件格式**

[Reference link](http://www.genome.ucsc.edu/FAQ/FAQformat.html) ：[http://www.genome.ucsc.edu/FAQ/FAQformat.html](http://www.genome.ucsc.edu/FAQ/FAQformat.html)_                
_

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

[Download link1](https://www.jianguoyun.com/p/DVKrG8QQ0NLuBRjJz0Y)

[Download link2](assets/Saccharomyces_cerevisiae.R64-1-1.77.gtf.gz)

3） 下载方法3：  
该文件在"[虚拟机](https://pan.baidu.com/s/1ETkey)"中已经下载好，位置在/home/cs/Bioinfo\_Lab/0.Linux/myfolder下，文件名为  Sa\*.gtf.gz  
可以考到自己目录下：

```
cp /home/cs/Bioinfo_Lab/0.Linux/*.gtf.gz  .
```

> **Note:**  
> 星字符：\* 可以代表任何字符，称为wildcard。

**1.2.3** 解压缩

首先将\*.gtf.gz放到自己创建的目录下（可以使用cp或者mv命令），  
然后解压缩该文件：

```bash
gunzip *.gtf.gz
```

> ** Tips **
>
> **1\) 命令cp、文件“./\*.gtf.gz”、目录“my\_folder/”之间均存在空格。**
>
> **2\) 在Linux命令行中， "." 可代表当前目录，".."可代表上一层目录。**
>
> **3\) tab键可以实现命令名及文件名的自动补全。**

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

`vi run.sh`

rush.sh的文件内容：

```
#!/bin/bash   
grep exon *.gtf | awk '{print $5-$4+1}' | sort -n | tail -3
```

（第一行语句一般用来声明这个脚本使用的shell名称，“\#”后的语句可作为批注，在执行时会被忽略）

关闭vi编辑器，返回命令行后键入：

```
chmod +x run.sh
./run.sh
```

### 上机作业：

---

1. 查找、理解并注释上述每一个语句和参数的意义

2. 解释gtf/gff文件中第4、5列（$4,$5\)代表什么，exon长度应该是$5-$4+1还是$5-$4？

3. 有新的方法加分，但必须注释清楚每个语句和参数的意义和结果。

### 

### 更多阅读和练习

---

* [**相关教学视频**](http://list.youku.com/albumlist/show/id_51618375.html)：Week I. 2. Linux

* **for Beginners **
  * 阅读和练习《鸟哥的Linux私房菜-基础学习篇》如下章节:
  * 《“笨办法”学python》附录“命令行快速入门”  

> 第5章  
>  5.3.1 man page  
> 第6章  
> 6.1用户与用户组  
>   6.2  LINUX文件权限概念  
>   6.3  LINUX目录配置  
> 第7章Linux文件与目录管理  
> 7.1目录与路径  
> 7.2文件与目录管理  
> 7.3文件内容查阅  
> 7.5命令与文件的查询  
> 7.6权限与命令间的关系  
> 第8章  
> 8.2文件系统的简单操作  
> 第9章  
> 9.1压缩文件的用途与技术  
> 9.2 Linux系统常见的压缩命令  
> 9.3打包命令：tar  
> 第10章vim程序编辑器  （或者其他编辑器文档）  
> 第11章 认识与学习bash  
> 第25章 LINUX备份策略  
> 25.2.2完整备份的差异备份  
> 25.3鸟哥的备份策略  
> 25.4灾难恢复的考虑  
> 25.5重点回顾
>
> 第11章 认识与学习bash  
> 第12章 正则表达式与文件格式化处理  
> 第13章 学习shell script

* **for Advanced Readers **

&lt;&lt;Bioinformatics Data Skills&gt;&gt;

> 3\) Remedial Unix Shell



