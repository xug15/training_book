# **Mapping, Annotation **and** QC**

---

### Install bioinformatics software in Linux \(centos\)

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



