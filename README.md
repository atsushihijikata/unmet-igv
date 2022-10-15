# About UNMET

UNMET stands for UNified METrics for unmappable, undetectable and unreliable genomic loci with short-read NGS.

The UNMET score represent a validity measurement metric of degree in variant detection for each base in the genome sequence. The score ranges [0, 1] and if it closes to 1 it means a difficulty in variant detection using short-type NGS. 


## Visualization of UNMET score using IGV

The UNMET score for each CDS segment is visualized with Integrated Genome Browser (IGV). The session file (.xml) can be loaded from the File Menu of IGV.


#### Usage

1. Download Zipped file of this repository from 'Code' shown above the github page.
2. Download [IGV](https://software.broadinstitute.org/software/igv/download).
3. Launch IGV on your desktop PC.
4. From the 'File' menu on IGV, select 'Open Session...' and open the IGV session file (UNMET_igv_session.xml).

#### Example
<img width="1467" alt="UNMET-igv-snapshot" src="https://user-images.githubusercontent.com/2074467/115367252-02c40580-a201-11eb-9133-4eab9bdbe22e.png">


#### Feature trucks

* UNMET score
	* It represents a degree of the unreliability of variants if a variant is found on the genomic position, ranging from 0 to 1. A higher value means a high degree of difficulty in detection of genomic variant.

* Standardized genome sequencing coverage in gnomAD
	* Standardized absolute of the median genome coverage in [gnomAD v3.1](https://gnomad.broadinstitute.org/downloads).

* Genome coverage of exome data in gnomAD
	* The median value of sequencing coverage in [gnomAD v2.1.1](https://gnomad.broadinstitute.org/downloads). If a value greater than 100 it set to 100.

* Genome mappability マッパビリティ
	* The genome mappability is a metric for a read is uniquly mapped on a single position.
	* It calculated by using [GenMap](https://academic.oup.com/bioinformatics/article/36/12/3687/5815974) software with read length = 150bp and allowed mismatches = 2.

* Tandem repeats
	* The data was calculated with [TandemRepeat Finder(TRF)](https://academic.oup.com/nar/article/27/2/573/1061099).

* Homo-polymers
	* The contiguous segment with 7 or more single base.

* Low complexity region (LCR)
	* The LCR regions were calculated with [Symmetric DUST](https://www.liebertpub.com/doi/10.1089/cmb.2006.13.1028?url_ver=Z39.88-2003&rfr_id=ori:rid:crossref.org&rfr_dat=cr_pub%20%200pubmed).

* Gene expression
	* The gene expression value (TPM) of each exon were from the [GTEx v8](https://gtexportal.org/home/) data. The values depict the maximum TPM value among the tissues.

* ALT loci
	* Human Alternate loci information from the UCSC Genome browser.

* Structural variants
	* The information was obtained from [DGV (Database of Genomic Variants)](http://dgv.tcag.ca/dgv/app/home).

* Segmental duplication
	* The segmental duplication information was obtained from the UCSC Genome browser.
	* The data were classified into three groups by sequence similarity (>99%, >98%, <98%).

　



