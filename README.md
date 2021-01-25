# Project 1: Cell Hashing to Demultiplex Cells at the Single Cell Resolution

In this project, I've reanalyzed the data generated from the published paper https://genomebiology.biomedcentral.com/articles/10.1186/s13059-018-1603-1.

The published paper is saved in the 'Paper' folder.    
The Rmd and html scripts are saved in the 'Script' folder.    
The figures generated from the script are saved in the 'Figures' folder.

The authors of this paper introduce a new method for scRNA-seq multiplexing, where cells are labeled with sample-specific oligonucleotide tagged antibodies (HTOs) directed against immune surface markers (CD45, CD98, CD44, and CD11a). These HTOs contain unique 12bp barcode that can be sequenced alongside the cellular transcriptome.

The experiment was designed in a way where CITE-seq and Cell Hashing was performed simultaneously, yet generating separate sequencing libraries. In their proof-of-principle experiments, they obtained peripheral blood mononuclear cells (PBMCs) from eight separate human donors (donors labelled A through H) and each sample was stained with a different HTOs-conjugated antibody. The samples were pooled and run in a single lane on the 10X Genomics Chromium Single Cell 3' v2 system; expecting a yield of 20,000 single cells and generation of transcriptome, HTO, and ADT libraries. The cells were sequenced on the Illumina platform and the demultiplexing step was performed using the Seurat software.

**Highly expressed HTOs**       
Based upon the maximum HTO signal, HTO-A and HTO-B seem to be the most highly expressed.

![](Figures/Ridgeplot.png)

**Mutual exclusivity of HTO-A and HTO-B**    
Observing the Feature Scatterplot between HTO-A and HTO-B, one can observe that there isn't mutual exclusivity between the HTOs.

![](Figures/Scatterplot.png)    

**Comparing the number of UMIs**    
The number of UMIs for Doublets and Negatives are less as compared to Singlets.

![](Figures/violinplot.png)

**tSNE representation of the HTO classification**    
The tSNE plot shows how Singlets are separated from Doublets.     

![](Figures/tsne.png)

**Heatmap to represent the HTOs**    
The heatmap shows how the majority of the HTOs are exclusive for a specific patient sample.

![](Figures/heatmap.png)

Hence, this paper provides a very good and efficient approach for demultiplexing cells from multiple samples. This can help us to mix multiple samples with multiple different conditions and run them on the same 10X Chromium chip.
