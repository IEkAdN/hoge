# hoge

## Usage
In order to run BactSNP with default settings,  

```bactsnp -q <fastq list> -r <reference> -o <output directory> [options]```

Options:  
```-h | --help```  
Show this help message.  
```-v | --version```  
Show version information.  
```-q | --fastq_list FILE (either or both of -q and -a is required)```  
TSV file to specify the name and the pair of read-data files (FASTQ) of each isolate. When you have multiple FASTQ files for each strand, concatenate them into one file. See others/fq_list_format.  
```-r | --reference FILE```  
FASTA file of the reference sequence.  
```-o | --out_dir STR (required)```  
Name of output directory.  
```-j | --jobs INT (default: 1)```  
Number of concurrent jobs, i.e. number of isolates processed concurrently.  
```-t | --thread INT (default: 1)```  
Number of threads in platanus_trim, platanus, bwa mem, and samtools sort.  
```-a | --fasta_list FILE (either or both of -q and -a is required)```  
TSV file to specify the name and the assembly-data file (FASTA) of each isolate. Use this option when you do not have read data for some isolates. BactSNP simulates sequence reads from the input assembly and use them in the same way as the real sequence data. See others/fa_list_format.  
```--reference_strain STR```  
Name of a taget isolate used as a reference. BactSNP de novo assembles the genome of the specified isolate and uses it as the reference genome.  
```--mask_region FILE```  
TSV file to specify the region where you want to avoid calling SNPs. See others/input_region_format.  
```--dist_from_indel INT (default: 5)```  
If distance from the nearest indel is this value or smaller, an ambiguous allele is called.  
```--allele_freq FLOAT (default: 0.9)```  
If allele frequency is smaller than this value, an ambiguous allele is called.  
```--depth FLOAT (default: 10)```  
If coverage depth is smaller than this value, an ambiguous allele is called.  
```--no_clean```  
If this option is specified, BactSNP does not remove intermediate files.
