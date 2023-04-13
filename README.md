# RNA-seq-pipeline
A RNA-seq full pipeline from sequence reads to differential expression of genes 

Tools used:

* SRA toolkit
* FASTQC 
* MultiQC
* CutAdapt 
* STAR
* samtools
* IGV 
* featureCounts
* DESeq 2 
* ggplot2 
* EnhancedVolcano
* ComplexHeatmap

In this pipeline I show how to find and visualize statistical significant differential expression genes (DEGs) starting with
raw reads from Illumina sequencer. The dataset is a RNA-seq study in *Drosophila melanogaster* divided in two conditions:

    * Pasilla (PS) genes treated with RNAi (RNA interference)
    * untreated PS genes
   
The biological samples are varied between single-end and paired-end, by having or not technical replicates and by read length. Below, a breaf description of the biological samples used: 

![pca](https://user-images.githubusercontent.com/101593641/231793122-3be56ca5-d1ac-466b-942d-ca09597eb22e.png)

At the end of this pipeline/tutorial, we will have identified the most differentially expressed genes between Treated (PS silenced)  and Untreated condition:

![heatmap](https://user-images.githubusercontent.com/101593641/231786586-3c42fd91-6bf3-485d-819c-c31db8eee7a5.png)
![volcano](https://user-images.githubusercontent.com/101593641/231786598-bd4fe139-5b6f-40c1-9b7b-cd55a7c2b33e.png)

First, we process the reads and remove adapters and bad quality reads. Then, checking the overall quality of each biological sample we will achieve the following result:
![read_lengths](https://user-images.githubusercontent.com/101593641/231788577-651a75c5-5019-4ad7-a631-c5a0cf0027ad.png)

We map the processed reads with STAR aligner: 
![star](https://user-images.githubusercontent.com/101593641/231788971-5369bb73-4f06-4bcd-894a-9bc827a3d252.png)

And visualize the aligned reads to the reference genome, checking for splice junctions with IGV:
![igv](https://user-images.githubusercontent.com/101593641/231789255-afe47cd5-f516-479c-b215-f35f49d496fc.png)



References:
This pipeline is based on [Galaxy training tutorial](https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html)

Dataset source:  Brooks, A. N., L. Yang, M. O. Duff, K. D. Hansen, J. W. Park et al., 2011 Conservation of an RNA regulatory map between Drosophila and mammals. Genome Research 21: 193–202
