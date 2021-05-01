
# beagle installation 
module load python/3.6-conda5.2
conda create -n beagle -c bioconda beagle
conda install -c bioconda beagle 
conda install -c bioconda/label/cf201901 beagle
source activate beagle
beagle
## attempted beagle #"Unable to access jarfile /programs/beagle/beagle.jar"
java -Xmx10g -jar /programs/beagle/beagle.jar gt=filtered.vcf nthreads=10 iterations=12 out=imputed_file
#Unable to access jarfile /programs/beagle/beagle.jar

## run haplotype Genomic selection pipeline
https://animalgene.umn.edu/sites/animalgene.umn.edu/files/gvchap_linux_0.zip
unzip gvchap_linux_0.zip