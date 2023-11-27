# Download data 

The data pages are on Canvas on the section labled "Data for Workshops"

[DIR] annotation       - bakta and prokka outputs    
[DIR] assemblies       - flye fasta assemblies in one place    
[DIR] fastqc           - fastqc report for raw fastq in `/raw`  
[DIR] flye             - flye assembly output dir  
[DIR] quast            - quast report for flye assemblies  
[DIR] raw              - raw data files  


Use `wget` to download files you need for example:
```
wget https:<www.thewebpage/practical/reads/example.fastq> .
```
NOTE: 
> You can download a whole folder by using -r the line below will download the dir "Example"
```
wget -r https://cgr.liv.ac.uk/454/acdarby/LIFE748/Example .
```
