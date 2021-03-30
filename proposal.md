General Description
	For one of my dissertation chapters I will be working with a population of diverse Plant Introductions(PIs) sampled from the 
	USDA Germplasm resources Information Network (GRIN). The plan is to do genome-wide association studies to identify 
	quantitative disease resistant loci using the population. The GWAS will be developed in greenhouse and field environments. Due
	to complexities of field studies for quantitative disease resistance to Phytopthora sojae I will be resticted to the number 
	of lines in my study. Ideally GWAS would be developed using a large diverse population. Therefore, in an attempt to maximize 
	GWAS potential with minimal population sizes and to fulfil the class requirements, I propose to do a population structure 
	analysis of the PIs using a 50K SNP BeadChip(soybean). Furthermore I plan to prepare haplotype genotypes by converting the format of the SNP genotypic file 
	into the format for BEAGLE which I will use to produce imputed haplotypes which will then be divided into haplotype blocks and haplotype genotypes will be 
	defined withen each block. These files will be prepared in order to run a pipeline for genomic prediction and variance component estimation using haplotypes
	and SNP markers as described by Prakapenka et al 2020. 
Technical aspects
	While there are packages available in R to do the population analysis I will be attempting to complete this in python. The genotype data is publicly available
	from Soybase. Soybase has a tool to extract genotype data for accessions of interest; however, I will extract the genotypes for select accessions from maturity groups II
	and III from the VCF file containing the data for all accessions available in the data base. I will need scripts to remove monomorphic markers, markers with > 5% missing
	data, and markers with a minor allele frequency of < 5% prior to analysis. I will need a script for the population structure analysis and one for the haplotype
	visualization. I plan to compare fastSturucture and Stucture, both written in python. I will prepare the haplotypes as described by Prakapenka et al 2020 which uses BEAGLE 
	to impute haplotypes and 'block-by-snp.py' to define haplotype blocks 
Project uncertainty 
	I am mainly uncertain of how I will be running the haplotype analysis. 
Reasoning
	I choose this as my final project because it will be useful to my research since I will be able to gain knowledge on the 
	diversity of my population. Additionally, it will allow me to practice the topics covered in the course by implementing them
	to my own studies. 
