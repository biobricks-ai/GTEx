# The Genotype-Tissue Expression [GTEx](https://gtexportal.org/home/documentationPage) project
>The Genotype-Tissue Expression (GTEx) project aims to provide to the scientific community a resource with which to study human gene expression and regulation and its relationship to genetic variation. This project will collect and analyze multiple human tissues from donors who are also densely genotyped, to assess genetic variation within their genomes. By analyzing global RNA expression within individual tissues and treating the expression levels of genes as quantitative traits, variations in gene expression that are highly correlated with genetic variation can be identified as expression quantitative trait loci, or eQTLs.

Biobricks.ai transforms GTEx into parquet files. 

# Data overview 
- This directory contains data obtained from the long read data from GTEx. GTEx is a project that contains gene expression data from numerous tissue and cell line samples from multiple donors. 
- The data is stored in parquet format. Descriptions for each column of each file in GTEx can be found below.
- The data was downloaded from: https://gtexportal.org/home/datasets

# Data Table List 
- `flair_filter_transcripts.parquet`
- `GTEx_8_tissues_snRNAseq_atlas_071421.public_obs.h5ad`
- `GTEx_8_tissues_snRNAseq_immune_atlas_071421.public_obs.h5ad`
- `LORALS_GTEx_v9_ase_quant_results.gencode.parquet`
- `LORALS_GTEx_v9_ase_quant_results.parquet`
- `quantification_flair_filter.counts.parquet`
- `quantification_flair_filter.tpm.parquet`
- `quantification_gencode.counts.parquet`
- `quantification_gencode.tpm.parquet`

# Description of Files 

### Data files

`flair_filter_transcripts.parquet`
> All transcripts (annotated and novel) identified using FLAIR. We first combined all samples, before filtering reads with respect to existing transcription start sites, and filtering the final set using transdecoder.
The columns of this file are in [GTF](http://useast.ensembl.org/info/website/upload/gff.html) format.
- seqname. Name of the chromosome or scaffold.
- source. Name of the program that generated this feature.
- feature. Feature type name, e.g. Gene, Variation, Similarity.
- start. Start position of the feature, with sequence numbering starting at 1.
- end. End position of the feature, with sequence numbering starting at 1.
- score. The score field indicates a degree of confidence in the feature's existence and coordinates. The value of this field has no global scale but may have relative significance when the <source> field indicates the prediction program used to create this annotation. It may be a floating point number or integer, and not necessary and may be replaced with a dot.
- strand. Defined as + (forward) or - (reverse).
- phase. The frame in a codon (if applicable) to which the base pair correspond.
- attribute. A semicolon-separated list of tag-value pairs, providing additional information about each feature.

`GTEx_8_tissues_snRNAseq_atlas_071421.public_obs.h5ad`

This file contains the snRNA sequencing data that is part of GTEx. This dataset is in h5ad format. For information on this file and its contents, please read [Scanpy's](https://scanpy.readthedocs.io/en/stable/) documentation. For more information, please refer to the [study](https://www.biorxiv.org/content/10.1101/2021.07.19.452954v1) that generated this data.

<!-- <details>
  <summary>obs</summary>
- n_genes                            
- fpr                                  
- tissue                           
- prep                               
- individual                         
- nGenes                               
- nUMIs                                
- PercentMito                          
- PercentRibo                          
- Age_bin                              
- Sex                                  
- Sample ID                            
- Participant ID                       
- Sample ID short                      
- RIN score from PAXgene tissue Aliquot
- RIN score from Frozen tissue Aliquot 
- Autolysis Score                      
- Sample Ischemic Time (mins)          
- Tissue Site Detail                   
- scrublet                             
- scrublet_score                       
- barcode                              
- batch                                
- n_counts                             
- tissue-individual-prep               
- Broad cell type                      
- Granular cell type                   
- introns                              
- junctions                            
- exons                                
- sense                                
- antisense                            
- intergenic                           
- batch-barcode                        
- exon_ratio                          
- intron_ratio                         
- junction_ratio                       
- log10_nUMIs                          
- leiden                               
- leiden_tissue                        
- Tissue composition                   
- Cell types level 2                   
- Cell types level 3                   
- Broad cell type numbers             
- Broad cell type (numbers)            
- Tissue                               
- channel
</details>

<details>
  <summary>var</summary>
  - gene_ids
  - Chromosome
  - Source
  - Start
  - End
  - Strand
  - gene_name
  - gene_source
  - gene_biotype      
  - gene_length"        
  - gene_coding_length
  - Approved symbol   
  - Approved name      
  - Status             
  - Previous symbols  
  - Alias symbols      
  - gene_include       
  - n_cells 
</details>

<details>
  <summary>var</summary>
  - gene_ids
  - Chromosome
  - Source
  - Start
  - End
  - Strand
  - gene_name
  - gene_source
  - gene_biotype      
  - gene_length"        
  - gene_coding_length
  - Approved symbol   
  - Approved name      
  - Status             
  - Previous symbols  
  - Alias symbols      
  - gene_include       
  - n_cells 
</details>

<details>
  <summary>uns</summary>
 - Broad cell type (numbers)_colors
 - Broad cell type numbers_colors
 - Broad cell type_colors
 - Broad cell type_logregcv_vae_colors
 - Broad cell type_sizes
 - Granular cell type_colors
 - Participant ID_colors
 - Sex_colors
 - Tissue composition_colors
 - Tissue_colors
 - dendrogram_['Broad cell type']
 - leiden
 - leiden_colors
 - leiden_sub_colors
 - neighbors
 - paga
 - prep_colors
 - tissue_colors
 - umap
 </details>
 
<details>
  <summary>obsm</summary>
 - X_pca
 - X_umap
 - X_umap_tissue
 - X_vae_mean
 - X_vae_mean_tissue
 - X_vae_samples
 - X_vae_var
 </details>

<details>
  <summary>varm</summary>
 - spring_leiden_sub
 </details>

<details>
  <summary>layers</summary>
 - counts
 </details>

<details>
  <summary>obsp</summary>
 - connectivities
 - distances
 </details> -->


`GTEx_8_tissues_snRNAseq_immune_atlas_071421.public_obs.h5ad`

This file contains the snRNA immune atlas data that is part of GTEx. This dataset is in h5ad format. For information on this file and its contents, please read [Scanpy's](https://scanpy.readthedocs.io/en/stable/) documentation. For more information, please refer to the [study](https://www.biorxiv.org/content/10.1101/2021.07.19.452954v1) that generated this atlas. 

`LORALS_GTEx_v9_ase_quant_results.gencode.parquet`
> Gene-wise haplotype counts per sample using the FLAIR annotation. Haplotype counts were obtained by running LORALS calc_asts.
- Gene. This column contains the chromosomal position of the allele and the Ensembl gene ID that the allele is found in, if applicable. 
- The following 61 columns are of the format `GTEX-'BARCODE'` where each 'BARCODE' corresponds to a separate sample. The values in each column correspond to the gene-wise haplotype counts per sample using the GENCODEv26 annotation. Haplotype counts were obtained by running LORALS calc_asts.

`LORALS_GTEx_v9_ase_quant_results.parquet`
> Gene-wise haplotype counts per sample using the FLAIR annotation. Haplotype counts were obtained by running LORALS calc_asts.
- Gene. This column contains the chromosomal position of the allele and the Ensembl gene ID that the allele is found in, if applicable. 
- The following 61 columns are of the format `GTEX-'BARCODE'` where each 'BARCODE' corresponds to a separate sample. The values in each column correspond to the gene-wise haplotype counts per sample using the FLAIR annotation. Haplotype counts were obtained by running LORALS calc_asts.

`quantification_flair_filter.counts.parquet`
> Raw counts quantification across transcripts for each sample using FLAIR transcripts. Quantifications was carried out using flair quantify.
- transcript. The name of the FLAIR transcript being quantified.
- The following 92 columns are of the format `GTEX-'BARCODE'` where each 'BARCODE' corresponds to a separate sample. The values in each column correspond to the raw counts quantification across transcripts for each sample using FLAIR transcripts. Quantifications was carried out using flair quantify.

`quantification_flair_filter.tpm.parquet`
> Normalised quantification (TPM) across transcripts for each sample using FLAIR. Quantifications was carried out using flair quantify.
- transcript. The name of the FLAIR transcript being quantified.
- The following 92 columns are of the format `GTEX-'BARCODE'` where each 'BARCODE' corresponds to a separate sample. The values in each column correspond to the normalised quantification (TPM) across transcripts for each sample using FLAIR. Quantifications was carried out using flair quantify.

`quantification_gencode.counts.parquet`
> Raw counts quantification across transcripts for each sample using GENCODEv26. Quantifications was carried out using flair quantify.
- transcript. The name of the FLAIR transcript being quantified.
- The following 92 columns are of the format `GTEX-'BARCODE'` where each 'BARCODE' corresponds to a separate sample. The values in each column correspond to the raw counts quantification across transcripts for each sample using GENCODEv26. Quantifications was carried out using flair quantify.

`quantification_gencode.tpm.parquet`
> Normalised quantification (TPM) across transcripts for each sample using GENCODEv26. Quantifications was carried out using flair quantify.
- transcript. The name of the Gencode transcript being quantified.
- The following 92 columns are of the format `GTEX-'BARCODE'` where each 'BARCODE' corresponds to a separate sample. The values in each column correspond to the normalised quantification (TPM) across transcripts for each sample using GENCODEv26. Quantifications was carried out using flair quantify.