Single Cell ATAC Seq Notes

after cellranger-atac mkfastq, there four fastq.gz files will be generated. I1, R1, R2 and R3. I1 is the 8 bp sample barcode, R1 is the forward read, R2 is the 16 bp 10x feature barcode and R3 is the reverse read. 


** Preprocessing
Demultiplexing  (scATAC-pro, cellranger)
Adapter trimming (scATAC-pro, Scasat, cellranger)


** Read mapping
BWA
Bowtie
Bowtie2


** Dimension reduction and visualization
PCA (scATAC-pro, cellranger)
LDA (scATAC-pro)
LSI (scATAC-pro, cellranger)
tSNE (scATAC-pro, Scasat, cellranger)
UMAP (scATAC-pro)
MDS (Scasat)
PLSA (cellranger)

** QC Metrics





** Final Plots

** Packages Abilities




** Peak Calling
ZINBA (cellranger)
MACS2 (scATAC-pro, Scasat)
GEM (scATAC-pro)
Binning (scATAC-pro)
COMBINED (scATAC-pro)




** Advanced Topics

10x uses quite different cell barcodes for scRNAseq and scATACseq applications.


