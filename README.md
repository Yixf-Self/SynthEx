### SynthEx

**SynthEx** is a comprehensive suite of tools for CNA detection and tumor heterogeneity profiling. 
It is tailored to cater for the multiple characteristics of different next generation sequencing technologies. 

**SynthEx** is the first method aware of the sample-specific bias in targeted regions due to fold enrichment differences in tumor and normal samples. Fundamentally different from current methods, it applies different analytical strategies for single subject and large-scale cancer genomics studies. For large-scale cancer genomics studies, it corrects the technical bias due to capture efficiency by using a "synthetic normal" strategy. The "synthetic normal" samples were generated by stratifying existing normal samples (including samples outside the current study) based on capture protocols. Therefore, instead of requiring a matched pair normal sample from each tumor subject, a "synthetic normal" is used that mimics the targeted sequencing profile with the same capture efficiency level as the tumor sample. This strategy can potentially reduce both the experiment and analysis burden within a sequencing facility. 

### Pre-processing and preparation

**SynthEx** takes counts data in non-overlapping genomic bins from tumor and normal samples as input. It  has  the  option  to  input  variant  calling  results  from  tumor  sample.   Thus **SynthEx** relies  on other tools to generate appropriate input files. We recommend **BEDtools** to get the bin-level count data and freebayes for variant calling.  In addition, **SynthEx** calls the **intersectBed** function from **BEDtools** directly, so **BEDtools** should be installed.  The helper function to process VCF files is written in **python**. So make sure **python** is installed on the system if applying the script.

### Installation

**SynthEx** relies on the following R packages: **mclust**, **flsa**, **foreach**, **DNAcopy**, **ggplot2**, **gridExtra**, **inline**, and **Rcpp**. Among these, **DNAcopy** is hosted on BioConductor and all the others are hosted on CRAN. 
  ```R
  install.packages ("mclust")
  install.packages ("flsa")
  install.packages ("foreach")
  install.packages ("ggplot2")
  install.packages ("gridExtra")
  install.packages ("inline")
  install.packages ("Rcpp")
  source("https://bioconductor.org/biocLite.R")
  biocLite()
  biocLite("DNAcopy")
  ```

**SynthEx** can be installed from github directly as follows:

  ```R
  install.packages ("devtools")
  library(devtools)
  install_github("ChenMengjie/SynthEx")
  ```
  
### Tutorial

A tutorial with examples illustrating the usage of **SynthEx** is distributed together with the package, also available at: https://github.com/ChenMengjie/SynthEx/blob/master/inst/doc/SynthExUserGuide.pdf. 
After installation, the tutorial can also be invoked by **SynthExUserGuide()**. 


### Author

**Mengjie Chen** (U Chicago)

Bug report, comments or questions please send to mengjiechen@uchicago.edu.
