# Additional instructions the instructor will need to try and rerun your project.
The markdowns should allow you to rerun the code pretty smoothly. There are two markdowns for fastStructure. one of them (my_lines) is for the population structure of my select lines(+900). The "all_accessions" is for population analysis of all the accessions left in the germplasm collection after I removed my lines ("=collection-my_lines"). For my_lines I was getting the wrong results due to how I was calling choosek.py. I realized this since it was giving me a result of k=3 and a seperate PCA suggested 14. The correct results I was able to get after changing the prefix of thee structure.py output and are here fs/ess/PAS1855/users/diaz335/final_project/my_lines/faststructure/test1.

Also havent been able to get beagle to run.

# You want to alert the instructor to some files files in the repository that should be ignored.
In my OSC repository "final_project" there will be a faststructure directory which were I was originally trouble shooting. The results and files for my analysis will be in the "minus_accessions" or "my_lines" directory. Other files in there include bcftools, htslib(samtools), vcftools(PLINK) which were needed to convert or fix the file formats. proj is an example of running fastStructure obtained from the source git. The linux directory is to download the package needed to do the haplotype analysis(my next step).

# You want to explain why you don’t have a functioning script or Snakefile, or why you didn’t run any SLURM jobs (which can be acceptable in some cases).

I was planning on having a functioning Snakefile and breaking the code into "extract>format>structure.py>choose.py> distruct.py" but was not able to get Snakefile to function correctly. I was attempting to do a loop at the structure.py stage to run through K 1-15 but was having trouble and due to time issues I choose to just do one markdown to run the scripts.