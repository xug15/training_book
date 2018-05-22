# Practice Guide

## 1\) 上机指南

Linux命令行格式：命令 _（空格）_【选项】_（空格）_参数1 参数2...

注意：命令、选项、参数之间一定要用**空格**来区分！

常用命令：

man 查询某一命令的具体参数，例如：`man wget`

或者 --help, 例如 `ls --help`

mkdir 创建文件夹

cd 目录切换（区别相对路径与绝对路径）

ls 显示文件夹中文件列表

cat 直接查看文件

wc 查看文件行数、字数

cut 取出文件中的特定列或字符

sort 排序

uniq 去重复

grep 文件中关键词搜索，返回行

chmod 修改文件的访问权限

> Note:
>
> 更多Linux命令使用指南详见[附录](appendix.md)

## 2\) 上机任务

**Linux基础和基因组注释文件解读**

### 1. 了解基因组注释文件 \(gff/gtf\)

**1.1 了解gff和gtf文件格式**

[Reference link](http://www.genome.ucsc.edu/FAQ/FAQformat.html) ：[http://www.genome.ucsc.edu/FAQ/FAQformat.html](http://www.genome.ucsc.edu/FAQ/FAQformat.html)    
__

**1.2 下载yeast的基因组注释文件**

**1.2.1** 先创建一个自己的文件夹

```text
mkdir my_folder
```

**1.2.2** 下载

1） 下载方法1： 可以从terminal下载：

```text
wget http://www.ncrnalab.org/lulab/public/1.gtf.gz
```

2） 下载方法2： yeast基因组注释文件可以从浏览器下载：

[Download link1](https://github.com/lulab/training_book/blob/master/.gitbook/files/Saccharomyces_cerevisiae.R64-1-1.77.gtf.gz)

[Download link](https://www.jianguoyun.com/p/DVKrG8QQ0NLuBRjJz0Y)2



3） 下载方法3：  
该文件在"[虚拟机](https://pan.baidu.com/s/1ETkey)"中已经下载好，位置在/home/cs/Bioinfo\_Lab/0.Linux/myfolder下，文件名为 Sa\*.gtf.gz  
可以考到自己目录下：

```text
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

> **Tips** 
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

### 2. 学会使用一个文本编辑器\(vi, nano, emacs\)编辑新的文件

写一个可执行文件，寻找长度最长的3个exon, 汇报其长度。

命令示范：

`vi run.sh`

rush.sh的文件内容：

```text
#!/bin/bash   
grep exon *.gtf | awk '{print $5-$4+1}' | sort -n | tail -3
```

（第一行语句一般用来声明这个脚本使用的shell名称，“\#”后的语句可作为批注，在执行时会被忽略）

关闭vi编辑器，返回命令行后键入：

```text
chmod +x run.sh
./run.sh
```

