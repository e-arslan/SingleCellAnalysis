# singlecell.csv

## Mapping results:
                          
"duplicate" : number of duplicate read-pairs                    
"chimeric" : number of chimerically mapped read-pairs                       
"unmapped" : number of read-pairs with at least one end not mapped                     
"lowmapq" : number of read-pairs with <30 mapq on at least one end                         
"mitochondrial" : number of read-pairs mapping to mitochondria and non-nuclear contigs  
"passed_filters" : number of non-duplicate, usable read-pairs i.e. "fragments"
"total" : is the  sum of all above

passed_filters is the important column


## Cell calling: 
"cell_id" : index of the barcode in cell barcodes. Appears as {species}_cell_{num}, otherwise None. (Why there is no hg19 in my singlecell.csv ??)               
"is__cell_barcode" : binary indicator of whether barcode is associated with a cell


## Targeting:
"TSS_fragments" : number of fragments overlapping with TSS regions     
"DNase_sensitive_region_fragments" : number of fragments overlapping with DNase sensitive regions
"enhancer_region_fragments" : number of fragments overlapping enhancer regions 
"promoter_region_fragments" : number of fragments overlapping promoter regions     
"on_target_fragments" : number of fragments overlapping any of TSS, enhancer, promoter and DNase hypersensitivity sites (counted with multiplicity)   
"blacklist_region_fragments" : number of fragments overlapping blacklisted regions


## Denovo targeting:
"peak_region_fragments" : number of fragments overlapping peaks
"peak_region_cutsites" : number of ends of fragments in peak regions

