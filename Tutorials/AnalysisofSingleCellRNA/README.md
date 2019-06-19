# SingleCellAnalysis

https://scrnaseq-course.cog.sanger.ac.uk/website/index.html

## Biological Terms that One should know
Transcriptomics: The study of transcriptomes and their functions.

Transcriptome: The transcriptome is the set of all RNA molecules in one cell or a population of cells. 

![Examples](images/G_schem.png)

Bulk RNA-seq : Measures the average expression level for each gene across a large population of input cells  
	* Useful for comparative transcriptomics, e.g. samples of the same tissue from different species  
	* Insufficient for studying heterogeneous systems, e.g. early development studies, complex tissues (brain)  
	* Does not provide insights into the stochastic nature of gene expression  

Single-cell RT-qPCR :

scRNA-seq : A new technology, first publication by (Tang et al. 2009)  
* Measures the distribution of expression levels for each gene across a population of cells.  
* Allows to study new biological questions in which cell-specific changes in transcriptome are important, e.g. cell type identification, heterogeneity of cell responses, stochasticity of gene expression, inference of gene regulatory networks across the cells.  
* Datasets range from 10<sup>2</sup> to 10<sup>6</sup> cells and increase in size every year
* Several computational analysis methods from bulk RNA-seq can be used
* In most cases computational analysis requires adaptation of the existing methods or development of new ones


## Workflow
Overall, experimental scRNA-seq protocols are similar to the methods used for bulk RNA-seq.

![Examples](images/RNA-Seq_workflow-5.jpg)

![Examples](images/moores-law.png)


## Computational Analysis
 The first steps (yellow) are general for any highthroughput sequencing data. Later steps (orange) require a mix of existing RNASeq analysis methods and novel methods to address the technical difference of scRNASeq. Finally the biological interpretation (blue) should be analyzed with methods specifically developed for scRNASeq.

![Examples](images/flowchart.png)

## Processing Raw scRNA-seq Data
1. Once you’ve obtained your single-cell RNA-seq data, the first thing you need to do with it is check the quality of the reads you have sequenced.






## R/Bioconductor

Github is also a version control system which stores multiple versions of any package. By default the most recent “master” version of the package is installed. If you want an older version or the development branch this can be specified using the “ref” parameter:


devtools::install_github("tallulandrews/M3D", ref="nbumi")
devtools::install_github("tallulandrews/M3Drop", ref="434d2da28254acc8de4940c1dc3907ac72973

* Source PAckage Installation
install.packages("M3Drop_3.05.00.tar.gz", type="source")


















































