This is the repository for the Practical Computing skills for biologists plntpth8300 spring 2021 final project 

# Project description
  What the project does as a whole.
The script allows for the extraction of select geneotypes from a VCF file containing Single Nucleotide Polymorphisms (SNPs) genotype information for over 20,000 soybean accessions. I used bcftools to extract accessions I will be working with for my dissertation. The selected population of 973 diverse Plant Introductions(PIs) was sampled from the USDA Germplasm resources Information Network (GRIN). FastStructure  population analysis using default settings was used to identify related population-groups. FastStructure is an algorithm for inferring population structure from developed especially large SNP genotype data. To choose the correct number of model components that explain structure in the dataset the algorithm was run for multiple choices of K values, that is the number of populations or clusters that your samples are best divided into. I then used choosek.py to choose the number of clusters k that best describes the clusters of my population. Choosek.py needs results from a range of K values so I ran structure.py with K values from 1-14. I used distruct.py to produce plots of the results. Using the results from choose K i specified the K units in distruct.py to tell it how many clusters represent my data. I also did this for the GRIN population minus the accessions I will be using to get an overall look at the population structure of the germplasm collection. 

  
# What each script does.
The Script extracts genotypes from a VCF file obtained from https://www.soybase.org/snps/ using bcftools. 
Fixes the vcf file using tabix from SAMtools. 
Fixes file containing list of select accessions. 
Filters select accessions from the VCF and converts to proper format (VCF -> PLINK bed)
Goes through the installation of fastStructure. 
Runs structure.py from fastStructure using a SLURM job script. 
Runs choose.py from fastStructure to select proper K unit to model components that explain structure in my data. 
Runs distruct.py to make plots to visualize results. 


# Where to access the data at OSC, assuming that the data is not in your repository.
The VCF file and file containing select samples can be found at: /users/PAS1707/diaz335/Data/faststructure/
This is the data needed to run the scripts.


# How the project’s scripts can be rerun using a single script or Snakefile.
The project's scripts can be run from the terminal. Conda environments will be needed for some steps. There is a Single script markdown that goes through the steps of the entire workflow.  


