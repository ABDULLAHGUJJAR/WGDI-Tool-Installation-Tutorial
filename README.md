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

![image](https://github.com/ABDULLAHGUJJAR/WGDI-Tool-Installation-Tutorial/assets/31093427/59c6e5ce-66a8-487a-82c6-7490fb03fd33)


