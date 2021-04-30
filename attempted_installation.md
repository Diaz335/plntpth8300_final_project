# Extracting genotype for samples 

# Download bcftools as described in their manual to extract sample's genotypes
#git init
#git clone --recurse-submodules git://github.com/samtools/htslib.git
#git clone git://github.com/samtools/bcftools.git
#cd bcftools
#autoheader && autoconf && ./configure --enable-libgsl --enable-perl-filters
#make\

# Fixing the vcf file header 
#  Download SAMtools as described in their manual 
#cd samtools-1.x    # and similarly for bcftools and htslib
##./configure --prefix=/where/to/install
#make
#make install
#export PATH=/where/to/install/bin:$PATH 



# Convert vfc to PLINK bed file #required by fastStructure
## tried using bedops with no luck
#conda create -n bedops-env bedops
#source activate bedops-env
#vcf2bed < filtered.vcf >genomic.bed
#convert2bed -i vcf < filtered.vcf > output.bed

## tried using R
#module load R/0.4.2-gnu9.1
#R
#x <- read.vcf(filtered.vcf)
#genomic.bed <- vcf2bed(x)


# Installing fastStructure as described in the manual
#mkdir /fs/ess/PAS1855/users/diaz335/final_project/proj
#cd /fs/ess/PAS1855/users/diaz335/final_project/proj
#git clone https://github.com/rajanil/fastStructure
#retrieve latest code updates
#cd /fs/ess/PAS1855/users/diaz335/final_project/proj/fastStructure
#git fetch
#git merge origin/master

#build python extensions
#export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/fs/ess/PAS1855/users/diaz335/final_project/
#export CFLAGS="-I/usr/local/include"
#export LDFLAGS="-L/usr/local/lib"

#set these environment variables.
#source ~/.bashrc 

#build library extensions
#cd ~/proj/fastStructure/vars
#python setup.py build_ext --inplace


## Failed attempt at installing fastStructure using conda to create environment
#module load  python/2.7-conda5.2
#conda create -y -n fastStructure-env fastStructure
#source activate fastStructure-env

## Another attempt at installing fastStructure #unsuccessful
#module install fastStructure
#module load fastStructure   