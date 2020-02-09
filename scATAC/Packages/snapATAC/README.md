## Step 1. Barcode selection

1) number of unique fragments: Taking the log10 of passed_filters (**number of non-duplicate,non-mit, high quality,nonchimeric usable read-pairs**)
2) fragments in promoter ratio: *promoter_region_fragments / passed_filters* meaning **(number of fragments overlapping promoter regions) / (number of non-duplicate,non-mit, high quality,nonchimeric usable read-pairs)** 

Filtering barcodes according to those values
Tutorial shows [3.5-5] for log10(UMI) and [0.4-0.8] for promoter ratio as cutoff
Personally not sure about the importance of the upper threshold for log10(UMI) so I used
[2-] for log10(UMI) and [0.2-0.8] for promoter ratio as cutoff


## Step 2. Add cell-by-bin matrix
Adding the cell-by-bin matrix of 5kb resolution to the snap object.

This super sparse matrix(dgCMatrix) is added to bmat of snap object. dgCMatrix class allows to compact that huge matrix. For instance if you wanna change the class of cell by bin to matrix, it expands from ~300MB to ~15GB.

## Step 3. Matrix binarization

Converting the cell-by-bin count matrix to a binary matrix. Some items in the count matrix have abnormally high coverage perhaps due to the alignment errors. Therefore, we next remove top 0.1% items in the count matrix and then convert the remaining non-zero values to 1.

## Step 4. Bin filtering
1) Filtering bins overlapping with the ENCODE blacklist.
2) Removing unwanted chromosomes 
3) The coverage of bins roughly obeys a log normal distribution. We remove the top 5% bins that overlap with invariant features such as the house keeping gene promoters.

Opt ) Removing any cells of bin coverage less than 1,000. The rational behind this is that some cells may have high number of unique fragments but end up with low bin coverage after filtering. This step is optional but highly recommanded.



