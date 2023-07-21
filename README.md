# WGDI-Tool-Installation-Tutorial
# WGDI Tool Installation for Mac, HPC, or Linux:

# 1. Installation:

WGDI (Whole-Genome Duplication Integrated analysis) is a Python-based command-line tool. It can be installed in Windows, Linux, and Mac OS operating systems via pip or conda.

# a. Using Bioconda (Recommended):

Bioconda is a bioinformatics package repository for Conda, a package manager primarily used for Python-based tools. To install WGDI using Bioconda, open a terminal or command prompt and execute the following commands:

       conda install -c bioconda wgdi

# 2. Dependencies:

WGDI relies on several third-party software packages for certain functionalities. These dependencies should be installed on your system before using WGDI. 

PAML: https://anaconda.org/bioconda/paml
      MAFFT: https://anaconda.org/bioconda/mafft
      MUSCLE: https://anaconda.org/bioconda/muscle
      PAL2NAL: https://anaconda.org/bioconda/pal2nal
      IQTREE: https://anaconda.org/bioconda/iqtree

If these dependencies were not installed with conda, you can install them manually and ensure they are accessible in your system's "PATH."

# 3. Usage:

After successful installation, you can use the WGDI tool via the command line interface (CLI). Open a terminal or command prompt and type the following command to see the available options and usage instructions:

      wgdi -h

This will display the help menu with information on how to run various workflows and analyses supported by WGDI.

# Citation:

If you use WGDI in your research or work, make sure to cite the original paper as follows:

Sun P., Jiao B., Yang Y., Shan L., Li T., Li X., Xi Z., Wang X., and Liu J. (2022). WGDI: A user-friendly toolkit for evolutionary analyses of whole-genome duplications and ancestral karyotypes. Mol. Plant. doi: https://doi.org/10.1016/j.molp.2022.10.018.

For the most up-to-date instructions and information, refer to the original source and documentation on the GitHub repository: https://github.com/SunPengChuan/wgdi.





#              WGDI Tutorial 2 
Python scripts to prepare files in the required format for the WGDI (Whole Genome Duplication Database Integration) Tool. It involves multiple steps, including converting files, generating karyotype files, and performing a BLAST search. Let's break down the instructions and clarify the steps:

# Step 1: Convert GFF3 files to BED format
Script: 01.getgff.py
                                         
                                          python 01.getgff.py Pyun.gff3 pyu.bed

## Explanation:
This script takes a GFF3 file named Pyun.gff3 as input and converts it into BED format, which has the columns 'chr', 'gene', 'start', 'end', and 'dir'. The output will be saved in a file named pyu.bed.

# Step 2: Convert BED format to WGDI required format
Script: 02.gff_lens.py
                                          
                                          python 02.gff_lens.py pyu.gff pyu pyu.gff pyu.lens
## Explanation:
This script takes the pyu.gff file (generated in Step 1) and converts it into the WGDI required format, assigning new names to genes and determining the order. It also creates a karyotype file named pyu.lens, containing chromosome names, lengths, and genes.


# Step 3: Convert CDS and protein files with new names
Script: 03.seq_newname.py

                                          python 03.seq_newname.py pyu.gff Pyun.cds pyu.cds.fasta 
                                          python 03.seq_newname.py pyu.gff pyun.pep pyu.pep.fasta
## Explanation:
These two commands run the script 03.seq_newname.py twice, each time taking pyu.gff as input and producing a different output file. The first command converts the CDS (coding sequence) file named Pyun.cds into a new FASTA file with renamed gene names, saving the result in pyu.cds.fasta. The second command does the same for the protein file named pyun.pep, producing pyu.pep.fasta with new gene names.

# Step 4: Perform BLAST search
Script: rundiamond.py

                                          python rundiamond.py ../pyu.pep.fasta ../../cor/cor.pep.fasta dbpycor pyu_cor.blast
## Explanation:
This script runs a BLAST search using the diamond program. It takes two input FASTA files, pyu.pep.fasta (generated in Step 3) and cor.pep.fasta from the cor directory. The database used for the search is named dbpycor, and the BLAST output is saved in the file pyu_cor.blast in the m6 format.
Please ensure that you have the required input files (Pyun.gff3, pyun.pep, Pyun.cds, pyu.gff, pyu.pep, and cor.pep.fasta) and the Python scripts (01.getgff.py, 02.gff_lens.py, 03.seq_newname.py, and rundiamond.py) in the correct locations before running these commands. Also, make sure you have the necessary dependencies installed for the Python scripts to work properly.

