# 1. Setup

How to do our jobs efficiently and reproducibly

### 0\) Get a Laptop or Desktop

---

[mac 使用技巧](https://www.evernote.com/l/ABIaUQq5Y4ZPv53w8iYevcDzHmCNY3AfIhU)

### 1\) Get a Linux OS

---

#### 1a\) docker or VM

[https://ygxing.gitbooks.io/docker/content/](https://ygxing.gitbooks.io/docker/content/)

#### 1b\) ssh & login {#ssh}

* ssh/sftp -p XXX \(default: 22\)
* ssh-keygen  \(authorized\_keys  id\_rsa.pub 权限设置为 600\)

> _**Tips:**_
>
> This will be very useful later when we work on remote machine as a local one, especially for jobs like **backup** and **script editing.**
>
> You can also using the following **SFTP/FTP  clients** to mount the remote server to the local desktop, so you can edit the scripts with a GUI editor like Atom:
>
> * Transmit
> * Fetch \(education version\)

### 

### 2\) Learn an Editor

---

#### A. **Vim** -- [Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)

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

### 4\)  Always backup data files regularly

---

> [Tips on 备份数据、保存中间数据 \| 数据安全](https://www.evernote.com/l/ABLaXPPQIg1FM5Kgl1AoLqLj67CR1Cv44ws)

**It's necessary to backup data regularly. **

### 5\)  github

---

**Setup:**

1\) add a setting file:

~/.gitconfig:

```
[user] 
email =[NNN@NN.com]
name = Shared
```

2\) Copy your ssh key to github website \([set up ssh key](#ssh)\)  
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

## More Readings

---

* &lt;&lt;Bioinformatics Data Skills&gt;&gt;



