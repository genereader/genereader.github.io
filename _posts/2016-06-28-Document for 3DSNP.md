# Documentation
## Overview
3DSNP is an integrated database for annotating the regulatory function of human noncoding SNPs by exploring their 3D interactions with genes and other SNPs mediated by chromatin loops. The model of cis-acting elements regulating gene expression through three dimentional interactions have been established recently. 3DSNP collects all currently available Hi-C datasets.
3DSNP integrates currently available Hi-C datasets of multiple human cell types with LD information from 1000 Genomes Project, chromatin state segments, transcription factor binding sites and  DNA accessibility from the Roadmap Epigenomics and ENCODE projects, DNA-binding motifs from Transfac and JASPAR databases, eQTLs from published studies and sequence conservation across mammals. Network- and Circos-based tools can be used to visualize interacting SNPs and genes along with important epigenetic marks. 3DSNP provides an integrated database and visualization tools for discovering the regulatory roles of noncoding SNPs and small indels varitants mediated by 3D genome topology. 
## Data source
### Sequential and genotyping data
3DSNP contains all 149,254,102 SNPs and small indels from NCBI dbSNP build 146. Among them, 84,801,880 SNPs were phased using 1000 Genomes Project Phase 3 (final phase) genotype data, the allele frequencies were obtained and pairwise LD was caculated for all pairs of SNPs in each continental population (AFR, AMR, ASN, EUR and SAS) within 200 kb. In addition, minor allele frequency (MAF) and linear closest gene were also extracted from dbSNP. Gene annotations were obtained from GRCh37/hg19 version of RefSeq genes from the UCSC Genome Browser(http://genome.ucsc.edu/).
### 3D genome topology
Chromatin loops identified by Hi-C technology in multiple human cell types were collected from published Hi-C studies to map the intrachromosomal interactions between distant genomic regions. (http://www.ncbi.nlm.nih.gov/pubmed/25497547; http://www.ncbi.nlm.nih.gov/pubmed/26499245; http://www.ncbi.nlm.nih.gov/pubmed/27053337). Chromatin interactions are classified into two types based on the spans of chromatin loops. For a chromatin loop shorter than 200 kb, the corresponding interaction type is ‘Within loop’, where genomic elements located within can interact each other. For a chromatin loop longer than 200 kb, the type is ‘Anchor-to-anchor’, where only elements located at the two anchors are supposed to interact with each other.
### Chromatin signature
A variety of chromatin signatures were used to annotate the regulatory functions of SNPs, including chromatin state (ChromHMM Core 15-state model), histone modifications (NarrowPeak), DNase I hypersensitivity sites and transcription factor binding sites from Roadmap Epigenomics and ENCODE projects. To annotate SNPs that alters TF binding motifs, TFM-Scan software was used to locate the putative TFBS across the genome using a set of position weight matrices (PWMs) collected from TRANSFAC and JASPAR databases. 
### Conservation
The conservation of SNPs were measured by phyloP score calculated from multiple alignments of 46 vertebrate species. PhyloP score for each nucleotide was downloaded from UCSC Genome Browser. In the phyloP plots, sites predicted to be conserved are assigned positive scores, while sites predicted to be fast-evolving are assigned negative scores. The absolute values of the scores represent -log(*P*-values) under a null hypothesis of neutral evolution.
### eQTL
eQTLs were also manually obtained from the GTEx analysis V6, the GEUVADIS analysis, and 10 other studies.
## Usage
### Query
Type the exact dbSNP id(s) of the interested SNP(s). Multiple SNP ids should be sperated by commas, and a comma is needed to complete the entering. In this mode, a text file containing a list of SNPs can be uploaded, and the assoication of these SNPs in LD (r2>0.8) will be displayed.
### Network-based visualization of associated SNPs in LD
A network-based plot is used to display a set of SNPs associated to the query in LD. By default, only the SNPs associated to the query directly are displayed (network distance = 1). Clicks the Dist=2 button to expand the network, in which SNPs indirectly associated to the query are also displayed. Network plots can be displayed in the browser and can also be downloaded as high quality PNG files.
### Circos-based visualization
A customizable Circos plot is developped to display the chromatin loops and a set of important chromatin marks surrounding the query SNP. Circos tracks from outside to inside represent: Chromatin states, RefSeq genes, DHS and histone modifications, TFBS, associated SNPs and chromatin loops. These chromatin marks are available for a wide cell types.
### UCSC Genome Browser-based visualization of chromatin signatures
## Tables
### Cell details
