# 2. Linux

## Part I.上机指南

---

Linux命令行格式：命令 _（空格）_【选项】_（空格）_参数1 参数2...

注意：命令、选项、参数之间一定要用**空格**来区分！

常用命令：

man 查询某一命令的具体参数，例如：`man wget`

mkdir    创建文件夹

cd    目录切换（区别相对路径与绝对路径）

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
> 更多Linux命令使用指南详见附录



### Examples
---
* grep

```
grep -v -c pattern FILES (-v exclude -c count lines)
grep -l pattern FILES (-l: list of the files)
```

* sed:

```
cat FILE | sed 's/\(.*\) cat \(.*\)/ \1 bat \2/’
```
 
* paste, cat and cut

```
paste FILES* > NEW_FILE;   cat FILES* > NEW_FILE
cut -f 2 FILE (-f: field)
cut -d ; -f 2 FILE (-d change delimiter)
```

* sort
```
sort at position 1, delimeter is ','; -r reverse sort
sort -t ',' -k 1 sort -r -t ',' -k 1
```

* rev and tac
```
echo john temp | rev     (output pmet nhoj)
tac    (reverse by lines)
```

* wc
```
ls * |wc -w   or  wc -l  (count the number of files)
```




### Tips

---

#### 1\) .bashrc and .bash\_profile

[example](https://github.com/lulab/PI/blob/master/workflow/bash_profile)

#### 2\) nohup, screen and qsub

* **nohup**:

`nohup nice -19 run.bat >& run.log&`

* **screen**: 
  * detach: ctrl-A, D
  * reattach: `screen -R -D `
  
* **qsub**: 
  * qlogin not allowed in some servers 
  * Check `qstat -u '\*' `
  * [example script](https://github.com/lulab/PI/blob/master/workflow/run_bins.pbs)

#### 3\)  secure your files

* make your files Read-only 
  * permission for a executable bash script is usually **755**
  * using `chmod -R a-w` for raw data and input files
* 777, rwxrwxrwx is forbidden \(using `chmod -R o-w`\)

* Change user group and permission

```
usermod –G admin  john  #  add sudo

usermod –G lulab  liyang  #  add to lulab group
chgrp –R  lulab  yourdir/
chmod –R  g+w   yourdir/

chmod  a+x  yourdir/
chmod  o+x  yourdir/
chmod  o-w  yourdir/
```

* Blocking the root:

vim /etc/ssh/sshd\_config  
  `#PermitRootLogin yes —>no`

#### 4\) System

* ssh-keygen  \(authorized\_keys  id\_rsa.pub 权限设置为 600\)

```
ssh-keygen -t rsa
copy authorized key in ~/.ssh/id_rsa.pub to remote_machine:~/.ssh/athorized_keys
```

> This will be very useful later when we work on remote machine as a local one, especially for jobs like **backup** and **script editing.**
>


* kernel version

```
uname -r 
uname -a 
```



* Edit text and view figures remotely

mount dir/ to local machine using NFS /sshfs/Transmit
 
```
$ yum install fuse-sshfs
$ usermod -a -G fuse john
sshfs john@nye:/Users/john /mnt/nyefs fusermount -u mountpoint
automounting: in /etc/fstab
sshfs#john@nye: /mnt/nyefs fuse uid=500,gid=100,allow_other 0 0
mount /mnt/nyefs; umnout /mnt/nyefs
```

* forward the log file to an email address

```
vim /home/.forward or /root/.forward
  zhi_lu@nnn.com
```
 


* Kill batch job 

```
ps -edalf | grep username 
kill -9 PID 
```


