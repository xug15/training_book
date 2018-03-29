# Perl/Python

How to program for bioinformatics

---

> We'll introduce both Perl and Python here. But you only need one for bioinformatics research.
>
> If you have no previous experience on either Perl or Python, we would recommend **Python** for you.

## Perl

---

### 1. Install Perl Modules

---

1. Install CPAN: [How to install CPAN modules](http://www.cpan.org/modules/INSTALL.html)
2. Install modules with cpan

usually you start cpan in your shell:

`# cpan`

and type

`install Statistics::Basic`

`install Statistics/LineFit.pm`

`install Math/Cephes.pm`

or in short form:

`cpan install Statistics::Basic`

`cpan install Statistics/LineFit.pm`

`cpan install Math/Cephes.pm`

##### 

##### Recommended Modules

* Bioperl :[ installation guide](http://bioperl.org/INSTALL.html)
* Statistics::Basic



### 2. Examples

---

[**My Perl Scripts at github**](https://github.com/lulab/PI/tree/master/MISC_scripts)** **

##### Favorites: {#perlf}

* [seqmanipulator.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/seqmanipulator.pl)
* [snp.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/snp.pl)
* [TFtargets.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/TFtargets.pl)
* [export\_intron.pl](https://www.gitbook.com/book/lulab/bioinfo-training/edit#)
* [siRNA-filter-NAR2008.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/siRNA-filter-NAR2008.pl)

## 

### 3. Tips

---

**Perl in command line**

```perl
perl -ne 's/aaa/ccc/;print $_' file.in
perl -p -i.bak -e 's/aaa/ccc/' file.in
perl -pi -e 's/aaa/ccc/' file.in
perl -n -e '@line=split(" ",$_);print $line[0] $line[1],"\n"' file.in
```

**Syntax checking**

perl -cw \*.pl

**Add perl5lib**

in .bashrc:

`export PERL5LIB=/home/john/my_perl_lib:/CVS/my_perl_lib`

**The state of a file**

```perl
use File::stat;
$sb = stat($filename);
print "$sb->size\n";
```

** In a subroutine **

`my $a = @_;`

is illegal to read the input. Must add \( \) to the variable, so it should be

`my ($a) = @_;`

### 4. Homework for Perl

---

1. Try to run [my favorite Perl ](#perlf)scripts and install the modules needed.

## 

## Python

---

[Additional Tutorial](https://shibinbin.gitbooks.io/bioinfomatics-training-program/content/python_basics.html)

