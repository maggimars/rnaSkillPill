# RNA-seq Skill Pill
### OIST - December 4th, 5th, 11th, 12th, 2019
#### Taught by: Maggi Mars Brisbin

### Course Resources

Github:

HackMd: https://hackmd.io/@maggi/RNA-Seq_SkillPill_Master

Stickies (Green = "everything is fine", Red = "I need some help" )


### Overview

RNA-seq is a widely used and extremely useful tool in biology, especially when working with non-model organisms that do not have published genomes. RNA-seq refers to using next-generation/high-throughput sequencing to sequence the mRNA in cell or tissue samples in order to determine which genes are being more or less expressed in certain conditions. RNA-seq can, therefore, provide insight into physiological states and molecular pathways associated with phenotypes of interest. In this Skill Pill, we will cover RNA-seq data analysis, starting with raw reads and ending with functional analyses (applicable to model and non-model organisms).


**Workflow:**


![](RNAseq.jpg)




wget

wget https://github.com/trinityrnaseq/trinityrnaseq/releases/download/v2.8.6/trinityrnaseq-v2.8.6.FULL.tar.gz
module load cmake
tar -xzf trinityrnaseq-v2.8.6.FULL.tar.gz
cd trinityrnaseq-v2.8.6/
make
make plugins

**Add**
PATH=$PATH:/path/to/trinity/installation/dir

to ~/.bashrc

/home/m/maggi-brisbin/RNAseq/trinityrnaseq-v2.8.6/Trinity

module load bowtie2/2.2.6


https://github.com/gmarcais/Jellyfish/releases/download/v2.3.0/jellyfish-2.3.0.tar.gz
tar -xzf jellyfish-2.3.0.tar.gz

cd

./configure --prefix=$HOME
make -j 4
make install
PATH=$PATH:/path/to/trinity/installation/dir

wget https://github.com/COMBINE-lab/salmon/releases/download/v1.0.0/salmon-1.0.0_linux_x86_64.tar.gz
tar -xzf salmon-1.0.0_linux_x86_64.tar.gz

**look at a zipped file**
 gzip -cd CONN.20111109.0057.gz | head


 ERROR:
 this is why we are running it as single end even though it is paired end
 https://github.com/trinityrnaseq/trinityrnaseq/issues/714

 ----
 fixing file names in yeast dataset

 for filename in *.fastq
do
  name=$(basename ${filename} .fastq)
  tr ' ' '_' <${name}.fastq >${name}.fq
done
