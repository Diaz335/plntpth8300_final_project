###extracting genotype for samples 

#Download bcftools as described in their manual
#git init
#git clone --recurse-submodules git://github.com/samtools/htslib.git
#git clone git://github.com/samtools/bcftools.git
#cd bcftools
#autoheader && autoconf && ./configure --enable-libgsl --enable-perl-filters
#make\

#Installing bcftools from conda 
module load python/3.6-conda5.2
source activate ipy-env
conda create -n bcftools-env bcftools
source activate bcftools-envy

#download the VCF file containing SNP data 
wget https://soybase.org/snps/soysnp50k_wm82.a2_41317.vcf.gz

#Run bcftools to filter samples in my population(listed in file.txt)

./bcftools view -S ^file.txt soysnp50k_wm82.a2_41317.vcf.gz > filtered.vcf #Did not run due to errors in file.txt and vcf file 


#Download SAMtools as described in their manual 
#cd samtools-1.x    # and similarly for bcftools and htslib
##./configure --prefix=/where/to/install
#make
#make install
#export PATH=/where/to/install/bin:$PATH 


#install SAMtools using conda 
module load python/3.6-conda5.2
source activate ipy-env
conda create -n SAMtools-env SAMtools
source activate SAMtools-env

#fixing the vcf file 
tabix -p vcf soysnp50k_wm82.a2_41317.vcf.gz


#Fixing the file.txt by Removing the whitespace
sed -E 's/\s*$//' file.txt > file.txt

#run bcftools 
./bcftools view -S ^file.txt soysnp50k_wm82.a2_41317.vcf.gz > filtered.vcf


###NEED to convert vfc to bed file 
#tried using bedops with no luck
#conda create -n bedops-env bedops
#source activate bedops-env
#vcf2bed < filtered.vcf >genomic.bed
#convert2bed -i vcf < filtered.vcf > output.bed



##tried using R
#module load R/0.4.2-gnu9.1
#R
#x <- read.vcf(filtered.vcf)
#genomic.bed <- vcf2bed(x)

nano 