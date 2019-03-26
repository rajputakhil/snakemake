# Snakemake - Tutorial

Snakemake is a workflow management system that aims to reduce the complexity of creating workflows by providing a fast and comfortable execution environment, together with a clean and modern specification language in python style. Snakemake workflows are essentially Python scripts extended by declarative code to define rules. Rules describe how to create output files from input files.

## Step 1: Install Miniconda 3

```sh
$ wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
$ bash Miniconda3-latest-Linux-x86_64.sh
```

When you are asked the question

    Do you wish the installer to prepend the Miniconda3 install location to PATH ...? [yes|no]

answer with __yes__. Along with a minimal Python 3 environment, Miniconda contains the package manager __Conda__.

After opening a new terminal, you can use the new conda command to install software packages and create isolated environments to, e.g., use different versions of the same package. We will later use Conda to create an isolated environment with all required software for this tutorial.

## Step 2: Using conda

A. Which conda env are installed

```
$ conda env list
```

B. Let's create a new environment called __bio__ and install the latest version of bwa, samtools, picard and bcftools

```
$ conda create --name bio bwa samtools picard bcftools
```

C. Install Snakemake with

```
$ conda install -c bioconda snakemake
```
from the Bioconda channel.

Or

Installing from Source

We recommend installing Snakemake into a virtualenv instead of globally. Use the following commands to create a virtualenv and install Snakemake. Note that this will install the development version and as you are installing from the source code, we trust that you know what you are doing and how to checkout individual versions/tags.

```
$ git clone https://bitbucket.org/snakemake/snakemake.git
$ cd snakemake
$ virtualenv -p python3 .venv
$ source .venv/bin/activate
$ python setup.py install
```