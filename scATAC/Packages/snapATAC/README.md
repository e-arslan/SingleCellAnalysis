## Step 1. Barcode selection

1) number of unique fragments: Taking the log10 of passed_filters (**number of non-duplicate,non-mit, high quality,nonchimeric usable read-pairs**)
2) fragments in promoter ratio: *promoter_region_fragments / passed_filters* meaning **(number of fragments overlapping promoter regions) / (number of non-duplicate,non-mit, high quality,nonchimeric usable read-pairs)** 

Filtering barcodes according to those values
Tutorial shows [3.5-5] for log10(UMI) and [0.4-0.8] for promoter ratio as cutoff
Personally not sure about the importance of the upper threshold for log10(UMI) so I used
[2-] for log10(UMI) and [0.2-0.8] for promoter ratio as cutoff
