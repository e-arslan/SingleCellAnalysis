## Single-cell multiomic analysis identifies regulatory programs in mixed-phenotype acute leukemia
Steps:  
1. QC   
	* TSS Enrichment - 8  
	* Unique Nuclear Fragments - 1000  
2. Count Tn5 corrected ATAC-Seq Insertion Sites for each single cell w.in 2.5kb windows
3. Binarize  windows for each single cell and TF-IDF transform & SVD (LSI) w top 20.000 accessible windows
4. SNN(Seuret) Clustering untilminumum of 200 cells per cluster
5. Create ATAC-Seq Tn5 insertion bed files  for each cluster then call peak summits w MACS2(q<0.05)
6. Use the  top 200.000 non-overlapping extended (+- 250bp) summits and identify the mostsignificant non-overlapping extended summits across  all clusters
7. Count Tn5 corrected ATAC-Seq Insertion sites for each single cell within each identified ATAC-Seq peak  to create  a counts matrix
8. Binarize peaks and compute TF-IDF transform and perform Singular Value Decomposition (LSI) w all accesible peaks
9. SSN(Seuret) Clustering, Cluster sums and compute logCPM normalize and then determine most variable peaks across clusters
10. Binarize Peaks for each single cell and compute TF-IDF transform and perform Singular Value Decomposition (LSI)w the most variable peaks.
11. SSN Clustering

### Thoughts
* Too many TF-IDF & SVD operations.
* TSS Enrichment > 8 is super high threshold for other datasets.
* SSN Clustering??

