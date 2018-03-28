# Perl/Python

How to program for bioinformatics

---

> We'll introduce both Perl and Python here. But you only need one for bioinformatics research.
>
> If you have no previous experience on either Perl or Python, we would recommend **Python** for you.

## Perl

---

### Install Perl Modules

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

### 

### Examples

---

[**My Perl Scripts at github**](https://github.com/lulab/PI/tree/master/MISC_scripts)** **

Favorites:

* [seqmanipulator.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/seqmanipulator.pl)
* [snp.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/snp.pl)
* [TFtargets.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/TFtargets.pl)
* [export\_intron.pl](https://www.gitbook.com/book/lulab/bioinfo-training/edit#)
* [siRNA-filter-NAR2008.pl](https://github.com/lulab/PI/blob/master/MISC_scripts/genomics/siRNA-filter-NAR2008.pl)

## 

### Tips

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

## 

## Python

---

Additional Tutorial

