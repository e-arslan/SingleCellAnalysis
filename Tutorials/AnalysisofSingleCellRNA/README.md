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


![Examples](images/RNA-Seq_workflow-5.jpg)
