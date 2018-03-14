# 3. Bash

How to set up multiple jobs as a pipeline

### 1\) github

---

#### \(1\) Desktop Version for Mac or Windows

I downloaded the [desktop version of github](https://desktop.github.com/) on mac.

#### \(2\) Terminal Version for Linux or Mac

**Setup:**

1\) add a setting file:

~/.gitconfig:

```
[user] 
email =[NNN@NN.com]
name = Shared
```

2\) Copy your ssh key to github website \([set up ssh key](/2linux.md#ssh-key)\)  
3\) Add a repository in github website

**Clone a repository:**

`git clone git@github.com:lulab/RNAfinder_Server.git`

**Add:**

```
git add exmaples/
git commit -a
git push origin
```

**Change:**

```
git commit -a
git push origin
```

**Remove:**

```
git rm *.file
git commit -a
git push origin
git pull?
```

[**more**](https://www.evernote.com/l/ABK7Gt9sva1CkLG9QfxqpZoog5uQoPDB_BU)

> **Case study**: how to use google to solve question
>
> * Q1: How to install terminal version of git in mac?
> * A1: google "[install git \_on \_mac](https://www.google.com.hk/search?safe=strict&q=install+git+on+mac&spell=1&sa=X&ved=0ahUKEwiin6jE1urZAhVFzWMKHfb5BuMQBQgjKAA)" --&gt; I got [the answer](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
>
> * Q2: After I installed git, I got such error:
>
> > xcrun: error: invalid active developer path \(/Library/Developer/CommandLineTools\), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun"
>
> * A2: google this whole sentence --&gt; I got [the answer](https://apple.stackexchange.com/questions/254380/macos-sierra-invalid-active-developer-path)

### 

### 2\) Examples

#### Example I

**install software and tools in a brand-new OS **

---

\(1\) 安装vim

```
yum -y install vim
```

\(2\) 打开一个空shell文件

```
vim myinstall.sh
```

\(3\) 复制如下shell脚本到smyinstall.sh内。此shell文件会自动安装包括：R-2.15.3，perl-5.26.1等

```bash
yum -y install wget
yum -y install readline-devel
yum -y install libXt-devel
yum -y install gcc gcc-c++
yum -y install gcc-gfortran
yum -y install libg2c.so.0
yum -y install less
yum -y install bzip2-devel
yum -y install zlib-devel
yum -y install xz-devel.x86_64
yum -y install make
yum -y install zip unzip

mkdir software
cd /software
wget -c https://cloud.r-project.org/src/base/R-2/R-2.15.3.tar.gz
tar -xvzf R-2.15.3.tar.gz
cd /software/R-2.15.3
./configure
make

cd /root
echo "export PATH=\"/software/R-2.15.3/bin:\$PATH\"" >> .bash_profile
source .bash_profile

cd /software
wget -c http://www.cpan.org/src/5.0/perl-5.26.1.tar.gz
tar -xvzf perl-5.26.1.tar.gz
cd /software/perl-5.26.1
sh Configure -de
make
make test
make install
```

\(4\) 执行shell脚本

```
bash myinstall.sh
```

#### 

#### Example II

**backup files using rsync and crontab**

---

\(1\) Prepare a backup script, for example, "_~/backup.sh_"

```bash
#!/bin/bash

RSYNC="rsync --stats  --compress --recursive --times --perms --links --delete --max-size=100M --exclude-from=/home/zl222/.rsync/exclude"

#1. Local backup  
#backing up /home1/zl222 to /home/zl222/sub_dir

echo "1. Backup of /home1/zl222 start at:"
date

$RSYNC /home1/zl222/ /home/zl222/backup_ncrna_home1/ 

echo "Backup end at:"
date



#2. Remote backup 

RSYNC="rsync --stats  --compress --recursive --times --perms --links --delete --max-size=100M --files-from=/home/backup1/backup_file"

echo "2. Backup 172.22.220.20:/data/ to /home/backup1/ start at:"
date

$RSYNC liushanhu@172.22.220.20:/data/ /home/backup1/

echo "Backup end at:"
date
```

\(2\) Using "crontab" command to execute the backup script routinely, and record in a log file, for example,

execute the command "_~/backup.sh &gt; ~/backup.log_" in 5:10am everyday:

```bash
1) open crontab and edit it by the following command: 

crontab -e  or crontab ~/cronjob

2) type in the following lines or write the following in a file (i.e. ~/crontab): 

# minute hour day_in_month month day_in_week command
     10   5  * * *   ~/backup.sh > ~/backup.log 

3) exit and save (like in VIM)
```

### 4\) Tips

---

* #### awk

  ```bash
  gawk '{print $2 $1}' FILE | head -100
  cat FILE | gawk '(NR>2) {print }'
  gawk -f FILE # take command from file

    Begin { a=1; ORS = ” ”}  # ORS: output record seperator
  ```
* #### input STANDIN in your script

```bash
rnatotal.o <<EOF
trna.lis
trna.out
trna
EOF
```



