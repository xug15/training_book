# 1. Setup

How to do our jobs efficiently and reproducibly

### 0\) Get a Laptop or Desktop

---

[mac 使用技巧](https://www.evernote.com/l/ABIaUQq5Y4ZPv53w8iYevcDzHmCNY3AfIhU)

### 

### 1\) Get a Linux OS

---

#### 1a\) docker or VM

```bash
#install and run a centos docker for the first time
docker pull centos
docker run -it --name=my_docker centos
or
docker run -it --name=container_name -v /HOST_ABSOLUTE_DIR:/CONTAINER_ABSOLUTE_DIR image_name:tag
useradd john
passwd john
su john
ctrl+p+q     # detach退出: 容器不关闭，容器内部正在运行的任务不会停止. ctrl+p+q表示按住ctrl不动，先按下p，后按下q

#re-attach the running container next time
docker ps  # get the container's name
docker attach container_name # attach进入
ctrl+p+q     # detach退出

#stop docker
docker stop container_id  # 关闭容器
```

More: [https://ygxing.gitbooks.io/docker/content/](https://ygxing.gitbooks.io/docker/content/)

#### 1b\) ssh & login

* ssh/sftp -p XXX \(default: 22\)

> You can also using the following **SFTP/FTP  clients** to mount the remote server to the local desktop, so you can edit the scripts with a GUI editor like Atom:
>
> * Transmit
> * Fetch \(education version\)

### 

### 2\) Learn an Editor

---

#### A. **Vim** -- [Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)

We also have [a brief version in Appendix](/1setup-appendix.md).

> Learn [vim](http://www.vim.org/) and it will be your last text editor. There isn’t any better text editor that I know of. It is hard to learn, but incredible to use.I suggest you teach yourself Vim in 4 steps:
>
> 1. **Survive**
> 2. Feel comfortable
> 3. Feel Better, Stronger, Faster
> 4. Use superpowers of vim

#### B. **Atom -- **[Tutorial and Tips ](https://www.evernote.com/l/ABJeb9FdBc1BC6AZSgWh4Ujc_StdcFYl-kw)

> A hackable text editor for the 21st century

### 

### 3\) README and MD

---

Document your project using markdown language \(available in wiki, gitbook, github, etc\)

### 

### 4\)  Always Backup Data Files Regularly

---

> [Tips on 备份数据、保存中间数据 \| 数据安全](https://www.evernote.com/l/ABLaXPPQIg1FM5Kgl1AoLqLj67CR1Cv44ws)

**It's necessary to backup data regularly. **

## 

## More Readings

---

* &lt;&lt;Bioinformatics Data Skills&gt;&gt;



