Single Cell ATAC Seq 

## Preprocessing
Demultiplexing  (scATAC-pro, cellranger)

Adapter trimming (scATAC-pro, Scasat, cellranger)


## Read mapping
BWA
Bowtie
Bowtie2


## Dimension reduction and visualization
PCA (scATAC-pro, cellranger)  
LDA (scATAC-pro)	
LSI (scATAC-pro, cellranger)	
tSNE (scATAC-pro, Scasat, cellranger)	
UMAP (scATAC-pro)	
MDS (Scasat)	
PLSA (cellranger)	

## QC Metrics





## Final Plots

#### Anchors builded_UMAP of scATAC and scRNA colored by cell type

#### coveragePlot for peaks CD8A_2nd most differential peaks


#### Motifs plot ATAC


#### PeriodPlot for different samples


#### pwf_Top5 enriched motif in cluster 0


#### scatter Plots between TSSEnrichment and number of unique fragments


#### top5 enriched motif in cluster0_smooth_k5


#### TSS enrichment Plots for each sample


#### UMAP co-embedded by tech


#### UMAP co-embedded


#### vlnPlot of features_afterBlacklistRatio




## Packages Abilities




## Peak Calling
ZINBA (cellranger) \
MACS2 (scATAC-pro, Scasat)
GEM (scATAC-pro)
Binning (scATAC-pro)
COMBINED (scATAC-pro)
