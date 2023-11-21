#Assembly workshop
##Note for conda setup

1. Create a Conda environment:
   ```
   conda create -n genomics_env
	```
	
2. Activate the environment:
   ```
   conda activate genomics_env
   ```
   
3. Add necessary channels:
```
   conda config --env --add channels bioconda
   conda config --env --add channels conda-forge
```

5. Install packages in the environment:
```
	conda install -c bioconda fastqc
  	conda install -c bioconda spades
	conda install -c bioconda flye
	conda install -c bioconda quast
```

# Testing install



### NOTE:
>We may use the software below later but do not install in the same conda environment. Remove `#` to use. 
```
#conda install -c bioconda checkm-genome
#conda install -c bioconda fastqc flye quast
#conda install -c bioconda porechop
```## 

