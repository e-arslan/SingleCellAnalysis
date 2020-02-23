## Multipotent RAG1+ progenitors emerge directly from haemogenic endothelium in human pluripotent stem cell-derived haematopoietic organoids  

January 06, 2020  

10x Genomics Chromium system  
1. Cell Ranger mkfastq and Cell Ranger count on each of the samples -->  filtered feature-barcode matrices MEX (filtered_gene_bc_matrices/hg38/matrix.mtx)
2. Quality control of the data and comprehensive analysis of the samples were performed on the basis of the tutorial guidelines provided by Satijilab.
3. After normalization of data in Seurat, we used the magic() function in its default format and included all genes for data diffusion. The MAGIC-imputed data were then subjected to further analysis in Seurat, similar to the original dataset.
4. The Monocole package in R was used for single-cell trajectory analysis.
5. Seurat objects were converted into a CellDataSet object. Low-quality cells were filtered out using the same criteria as specified in Seurat. Cells were classified into four groups: endothelial, haematopoietic, T cell and NKT cell on the basis of the markers indicated in Fig. 5f.
6. Cells marked as ‘Ambiguous’ or ‘Unknown’ were discarded. The remaining cells were used to generate a single-cell trajectory using the guidelines provided by the Trapnell laboratory




## Single-cell reconstruction of the adult human heart during heart failure and recovery reveals the cellular landscape underlying cardiac function
January 08, 2020

1. Raw reads were processed using the Perl pipeline script supplied by Takara. The main steps were as follows:
	* The validity of reads was checked. Only read pairs of which read 1 contains predefined barcode tag (10 nucleotides) and unique molecular identifier (UMI; 11–14 nucleotides) were retained.
	* Read pairs were filtered using cutadapt42 (v.1.8.1) with the following parameters: -m 20 -trim-n -max-n 0.7 --q 20.
	*  Reads were aligned to genomes of mouse, Escherichia Coli, mycoplasma, yeast and adapter sequences using bowtie2 (v.2.2.4)43. Contaminants were filtered by fastq_screen (v.0.5.1.4).  
	* Clean reads were mapped to the UCSC hg38 genome using STAR (v.2.5.2b)44 and assigned to Ensembl genes (GRCh38.81)45 using featureCounts (subread-1.4.6-p1 command line)46.
2. Minimal expression of 500 genes per cell; UMIs limited to 2 s.d. from the mean of log10 UMI of all cells; unique read alignment rate of >50%; and mitochondrial read percentage of <72% (mean + s.d.); and, for CMs from CM-enriched digests, at least 10,000 UMIs were required. 

3. To preclude the influence of the variation in mitochondrial genes (gene symbols starting with MT-) on downstream analysis, all of the reads that mapped to 37 mitochondrial genes were excluded. The UMI count of each gene was then divided by the total UMIs of the cell and multiplied by size factor 10,000 to obtain a transcripts per million (TPM)-like value. Then, the TPM-like value was transformed by the natural logarithm.

4. Clustering was conducted using Seurat (v.2.3.4)47. To avoid batch effects among samples and experiments, we used CCA in Seurat to align the samples.

5. A Seurat object was built for cells of each individual, and nUMI was regressed out using the Scale function. Variable genes among cells were then selected by their average expression level and dispersion—average log[TPM] was restricted to between 0.01 and 3 and dispersion was set as greater than 1. Variable genes that were present in at least two individuals were used as input for individual data alignment using the MultiCCA function with the parameter num.cc = 20. We observed that the first ten canonical correlation vectors could explain the majority of the correlation strengths, and were therefore used for subsequent cell clustering.

6. We applied an iterative clustering strategy as follows. (1) Total cell clustering: we used the FindClusters function of Seurat on the basis of the shared nearest neighbour (SNN-cliq) clustering method with parameters (k = 30, dim.use = 1:10, res = 1). Results were displayed by t-SNE plots and heat maps. The main cell types, such as CMs, ECs, FBs, MPs and SMCs, were determined according to the expression of known markers. (2) Sub-group cell clustering: for each main cell type, the cells were extracted and clustered separately. The first ten canonical correlations and resolutions of 0.8–2 were tested. By checking the expression heat map of markers of clusters (by FindAllMarkers function), a resolution value that could best distinguish clusters with a clear pattern was used. For normal EC, FB, MP and SMC cells, resolution = 0.8 was used. For other conditions, resolution = 1 was used.

7. Definition of marker genes of cell groups: The FindAllMarkers function was used with the parameters test.use=wilcox, min.pct=0.2, thresh.use=0.2, min.diff.pct=0.1, only.positive=TRUE and return.thresh=0.05. The genes were filtered with a q value of 1 × 10−6. For block differential expression analysis, such as comparing between CM and other cells, all of the subclusters were combined. For differential expression analysis among sub-group cells, each sub-group was compared with all of the other cells.

8. Cell transcription noise and similarity calculation: Transcription noise scores were calculated using a method published by Martin et al.50. First, a set of invariant genes were selected evenly across the range of mean expression. The genes were divided into ten equally sized bins by mean abundance, and 10% of genes with the lowest s.d. from each bin were selected, omitting the bins at the high and low extremes. Euclidean distance from each cell to the mean expression profile of all cells was calculated as a measure of transcription noise. For the cell similarity calculation, variable genes of target cells were selected using FindVariableGenes function of Seurat (dispersion cutoff 1). The average gene expression profile of a cell group was then calculated using previous genes as the centre. The Pearson correlation coefficient of each cell to the centre was calculated and shown as a box plot.

9. Cell–cell interaction network: Specifically expressed ligands and receptors of each cell cluster were detected using Seurat FindAllMarkers function by comparing each cell cluster to all other cells with q < 1 × 10−3. Ligands and receptors were then compared with the interaction data retrieved from the STRING database (9606.protein.links.full.v10.5)51 including 5,764,085 interacting pairs with experimental proofs. The interaction network graph (Fig. 4i,j) was drawn using ggplot2. Ligands and receptors were included in circles of cells as nodes. The interactions between genes were depicted as edges. Cells with most cell–cell interactions were placed at the centre of the interaction network, and surrounding cells were sorted according to their interaction connection counts in descending order.

10. Cell trajectory analysis: We used monocle2 (v.2.6.0)52 to study pseudotime trajectories of cells. The UMI matrix was used as input, and variable genes that were detected by Seurat were used for a building trace. For branch site differential genes analysis of CMs, the BEAM function was used to detect genes that contributed most significantly when cells branched (q < 1 × 10−3). KEGG pathway and GO enrichment analyses of DEGs were performed using clusterProfiler (v.3.2.14)53.

11. Cell clustering of normal and HF cells: The QC criteria used for filtering CMs from normal hearts were applied to HF samples. Normal cells and HF cells were combined using the MultiCCA method with num.cc = 20 and res = 1. A similar iterative clustering strategy was used. The new clusters (assigned as all_cell_cluster) were compared with the clusters defined by normal cells (normal_cell_cluster) using a voting method. In detail, for each cell in the all_cell_clusters, its most similar ‘ancestor’ in normal_cell_cluster was detected using Pearson correlation (correlation coefficient > 0.5). All of the ancestors of a new all_cell_cluster were then counted and the name of the biggest normal _cell_cluster source was used to represent the cluster. New clusters unique to all cell results were appended to the original classification. For differential expression analysis of normal LV, cHF LV and dHF LV CMs, the FindAllmarkers function was used with threshold p_val_adj < 1e-6 and avg_logFC > 0.25. The mean log[TPM] of genes was requested to be >0.1 in at least one condition.

12. Regulon analysis: The pysenic package (v.0.9.9, from DOCKER image hub)54 was used to predict regulon activity. The grn module was first used to build gene co-expression networks. The ctx module was then used to predict regulons. Finally, the aucell module was used to calculate activity of regulons in each cell. The motif files hg19-tss-centered-10kb-7species.mc9nr.feather, hg19-500bp-upstream-10species.mc9nr.feather and annotation file motifs-v9-nr.hgnc-m0.001-o0.0.tbl were used. For comparison of normal LV, LA and AV, all of the cells analysed were CMs. For comparison between normal LV cells, cHF LV cells and dHF LV cells, 400 normal LV CMs were sampled randomly to match the cell number of cHF LV (429 cells) and dHF LV (305 cells) samples.


## A Tppp3+Pdgfra+ tendon stem cell population contributes to regeneration and reveals a shared role for PDGF signalling in regeneration and fibrosis




























