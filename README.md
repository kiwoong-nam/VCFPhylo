# VCFPhylo
This script generates a distance matrix among individuals from a vcf file to generate a phylogenetic tree.

How to use:

<1> converting gz-compressed vcf file to genotype file

$ perl reducedvcf.pl VCF_FILE GENOTYPE_FILE
, where VCF_FILE is the file name of your gz-compressed vcf file and GENOTYPE_FILE is the name of output genotype file. When you finished running this script, GENOTYPE_FILE.gz will be created.

<2> creating distance matrixes from the gz-compressed genotype file.

$ perl VCF_FILE GENOTYPE_FILE OUTPUT_PREFIX NUMBER_OF_BOOTSTRAPPING_REPLICATES
, where VCF_FILE is the name of gz-compressed vcf file,and GENOTYPE_FILE is gz-compressed genotype file, OUTPUT_PREFIX is  output prefix, and NUMBER_OF_BOOTSTRAPPING_REPLICATES is the number of cootstrapping replication.

When you finished running this file, the following two files will be created.
  (a) OUTPUT_PREFIX.bg.tre
    => 


use strict;

my $inputvcf=shift;
my $distF=shift;
my $output=shift;
my $B=shift;

my $bg_output=$output.'bg.tre';
my $boot_output=$output.'boot.tre';

my @names;
my $nsamples;




