# RVHaplo
A viral haplotype reconstruction tool for long reads.



### E-mail: dhcai2-c@my.cityu.edu.hk
### Version: V1

### Dependencies:
* Conda
* Python >=3.6
* samtools >= 1.4.1
* Required python package: markov_clustering, pysamstats >= 1.1.2, networkx >= 2.5.1, pandas >= 1.1.3

#### Install Dependencies
`conda create -n rvhaplo python==3.6`<BR/>
`conda activate rvhaplo`<BR/>
`conda install -c bioconda samtools pysamstats`<BR/>
`pip install markov_clustering networkx pandas`<BR/>
####


## Usage

### Default
`./rvhaplo.sh -i alignment.sam -r reference.fasta`<BR/>

#### Options
`-o  | --out                Path where to output the results. (default:./)<BR/>
-p  | --prefix STR:                Prefix of output file. (default: rvhaplo)<BR/>
-e  | --error_rate FLOAT:         Sequencing error rate. (default: 0.1)<BR/>
-s  | --signi_level FLOAT:        Significance level for binomial tests. (default: 0.05)<BR/>
-c  | --cond_pro FLOAT:           Minimum conditional probability for a SNV site. (default: 0.65)<BR/>
-n1 | --num_read_1 INT:           Minimum # of reads for marginal probability. (default:10)<BR/>
-n2 | --num_read_2 INT:           Minimum # of reads for conditional probability. (default: 5)<BR/>
-g  | --gap INT:                  Minimum length of gap between SNV sites for conditional probability. (default:15)<BR/>
-s  | --smallest_snv INT:         Smallest # of SNV sites for haplotype construction. (default:20)<BR/>
-or | --overlap_read INT:         Minimum overlap between two reads in the read graph<BR/>
-wr | --weight_read FLOAT:        Minimum weights of edges in the read graph. (default:0.8)`<BR/>
-m  | --mcl_inflaction FLOAT:     Inflaction of MCL algorithm. (default:2)<BR/>
-l  | --lar_cluster INT:          A threshold to seperate clusters into two groups by sizes of clusters. (default:50)<BR/>
-oc | --overlap_cluster INT:      A parameter related to the minimum overlap between consensus sequences. (default:10)<BR/>
-d  | --depth INT:                Depth limitation for consensus sequences generated from clusters. (default:5)<BR/>
-wc | --weight_cluster FLOAT:     Minimum weights between clusters in the hierarchical clustering (default: 0.8)<BR/>
-a  | --abundance FLOAT:          Minimum abundance for filtering haplotypes (default: 0.005)'<BR/>
####

## Output Results
```
VirStrain - An RNA virus strain-level identification tool for short reads.

Example: python VirStrain.py -i Test_Data/MT451123_1.fq -p Test_Data/MT451123_2.fq -d VirStrain_DB/SCOV2 -o MT451123_PE_Test

required arguments:
    -i, --input_reads             Input fastq data.
    -d, --database_dir            Path of VirStrain database.

optional arguments:
    -h, --help                    Show help message and exit.
    -o, --output_dir              The output directory. (Default: ./VirStrain_Out)
    -p, --input_reads2            Input fastq data for PE reads
    -c, --site_filter_cutoff      The cutoff of filtering one site when calculate the Vscore. (Default: 0.05)
    -m, --high_mutation_virus     If the virus has high mutation rate (like HIV), use this option. (Default: off)
```
