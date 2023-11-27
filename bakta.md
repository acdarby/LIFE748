Genecalling and annotation using bakta



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

