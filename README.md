# OrthoMCLP
Parallel implementation of OrthoMCL


We have reimplemented the sections of OrthoMCL that rely on databases. This way, OrthoMCL could be ran in parallel for a large number of genomes.

Ehsan Tabari, May 19, 2015

The initial steps of OrthoMCLP are exactly the same as OrthoMCL.
We have reimplemented steps 7, 8 and 9. (main processing steps)

# Requirements

There are very few requirements for OrthoMCLP. Here are the list of the things needed to run OrthoMCLP

- Perl 5.x
- Python 2.x
- [BioPython](http://biopython.org/wiki/Download)
- [NCBI Blast](ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST)
- [MCL](http://www.micans.org/mcl/sec_description1.html)

Perl and Python come preinstalled on most Linux and Unix (OS X). You need to install them on Windows. 


# Steps 

The sample folder contains execution of all these steps. Each folder created at each step is numbered by the step number. 
The starting data is located in sample/0.input_faa

## Step 1: orthomclAdjustFasta

This is EXACTLY like the 5th step of OrhtoMCL.

You must run `orthomclAdjustFasta` on your input fasta files. orthomclAdjustFasta creates output in the same folder it's ran. 
The input arguments to orthomclAdjustFasta are:
- String to label each sequence
- Input Fasta file 
- A number identifying the field containing protein identification on the fasta header

```
orthomclAdjustFasta NC_000913 sample/0.input_faa/NC_000913.faa 4
```

If you have downloaded faa files from NCBI (for example: ftp://ftp.ncbi.nlm.nih.gov/genomes/Bacteria/all.faa.tar.gz)
We have supplied a bash script to run `orthomclAdjustFasta` on all faa files and produce the proper fasta files.

```shell
cd compliantFasta
orthomclAdjustFastaAll.sh <input_folder>
```
