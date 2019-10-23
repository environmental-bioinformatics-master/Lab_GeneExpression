# Lab_GeneExpression

First, hop onto Poseidon and open a new tmux session:
`tmux new -s diffex`

Navigate into your user folder for the class, and pull the "Lab_GeneExpression" Git repository:

git clone ????
cd Lab_GeneExpression

Request some interactive space on the HPC:
`srun -p compute --time=01:00:00 --ntasks-per-node=1 --mem=10gb --pty bash` 

Now, let's set up a conda environment to play in:

conda create --name diffex
conda activate diffex
conda install -c r r

This will install R in a conda environment. Nearly all gene expression analysis programs work in R, a higher-level coding language that is particularly good for statistics, data management, and plotting.

Open `R` interactively by typing:
`R`

Your prompt should change to a greater-than sign:
`>`

Much like python, a lot of the good stuff in R is done through "add-on" modules for more specialized tasks. In R, these are called packages.

*BONUS R factoid for baseball lovers: you can install the entire Sean Lahman Baseball Database in R if you want to try your hand at sabermetrics. The package is called `Lahman`, and it contains statistics from 1871-present.*

First, we need to install some packages we'll want to work with: `DESeq2` (which is used for differential expression), and `pasilla`, which contains an example gene expression data set. R packages are usually installed with this syntax: `install.packages("PACKAGE_NAME")`. Like so many things in UNIX, package names are case-sensitive.

Some specialty R packages are installed via a system called Bioconductor, and DESeq2 is one of those. If you try to install a package the regular way and it isn't found, google it and see if there are special installation instructions. To install the DESeq2 package, you need to first install the Bioconductor Manager package:
`install.packages("BiocManager")`

Before you can proceed, a list will pop up starting with:
`--- Please select a CRAN mirror for use in this session ---`
...and followed by a series of numbered locations. Pick one that's fairly close to you by typing its number. CRAN is the Comprehensive R Archive Network, a series of servers around the world that host up-to-date copies of R packages.

You will probably be asked if you want to use a local library for installation. Type `y`, and type `y` again to accept the default local library name suggested.

Now, you should be able to install DESeq2 via the Bioconductor package you just installed:
`BiocManager::install("DESeq2")`

*These installation instructions are clearly given on the Bioconductor page for DESeq2: https://bioconductor.org/packages/release/bioc/html/DESeq2.html*

There is a lot in DESeq2, so this will take a while and involve a lot of text.





