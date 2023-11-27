# Gene calling and Annotation

## Using gene calling and annotation software 

### Understand genome assembly quality via gene calling  


NOTE
>This document makes the assumption:
>- That you are working in a WSL terminal [installing WSL](WSL.md)
>- That you have installed conda and the required software [install conda](conda_install.md)

Data for this workshop can be found at [DATA](https://github.com/acdarby/LIFE748/blob/main/data_downloads.md)

ONT Salonella genome at X coverage:

| raw reads      |
| ---------------|
| S_ONT_longx30.fastq |
| S_ONT_shortx30.fastq |
| S_ONT_raw_longx30.fastq |
| S_ONT_longx10.fastq |
| S_ONT_longx100.fastq |

Pacbio Salonella genome at 30X coverage:
| raw reads      |
| ---------------|
| S_hifi_longx30.fastq |

the other data follow this pattern

### AIM 
> Pick a pair of assemblies from above for comparison
> e.g. S_ONT_longx30 vs  S_ONT_shortx30 or S_hifi_longx30 vs  S_ONT_longx30 or etc etc 
> - Use bakta and/or prokka to call genes on two genomes
> - Use artemis to view and review the genecalls


Create environment and install artemis and conda

``` 
conda create -n anno
conda activate anno 

conda config --add channels bioconda
conda config --add channels conda-forge
conda install artemis

conda install -c bioconda bakta
bakta_db download --output ~/tmp_data/ --type light
```

run bakta - using the light database and the sample you have selected 
```
bakta --db db-light GN3_hifix30_flye_assembly.fasta --output bakta/GN3_hifix30_flye_assembly
```

