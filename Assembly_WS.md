# Assembly workshop

NOTE
>This document make the assumption:
>- That you are working in a WSL terminal [installing WSL](WSL.md)
>- That you have installed conda and the required software [install conda](conda_install.md)
>- That you have run the command `conda activate genomics_env`
   
### We are using the assemblier called `flye` [Flye github](https://github.com/fenderglass/Flye)
```
flye --help
```
Can be used to remind you on the parameters we can provide/change:
```
flye
usage: flye (--pacbio-raw | --pacbio-corr | --pacbio-hifi | --nano-raw |
	     --nano-corr | --nano-hq ) file1 [file_2 ...]
	     --out-dir PATH

	     [--genome-size SIZE] [--threads int] [--iterations int]
	     [--meta] [--polish-target] [--min-overlap SIZE]
	     [--keep-haplotypes] [--debug] [--version] [--help]
	     [--scaffold] [--resume] [--resume-from] [--stop-after]
	     [--read-error float] [--extra-params]
	     [--deterministic]
flye: error: the following arguments are required: -o/--out-dir
(genomics_env) acdarby@gauss08:~/tmp_data$ flye --help
usage: flye (--pacbio-raw | --pacbio-corr | --pacbio-hifi | --nano-raw |
	     --nano-corr | --nano-hq ) file1 [file_2 ...]
	     --out-dir PATH

	     [--genome-size SIZE] [--threads int] [--iterations int]
	     [--meta] [--polish-target] [--min-overlap SIZE]
	     [--keep-haplotypes] [--debug] [--version] [--help]
	     [--scaffold] [--resume] [--resume-from] [--stop-after]
	     [--read-error float] [--extra-params]
	     [--deterministic]

Assembly of long reads with repeat graphs

options:
  -h, --help            show this help message and exit
  --pacbio-raw path [path ...]
                        PacBio regular CLR reads (<20% error)
  --pacbio-corr path [path ...]
                        PacBio reads that were corrected with other methods (<3% error)
  --pacbio-hifi path [path ...]
                        PacBio HiFi reads (<1% error)
  --nano-raw path [path ...]
                        ONT regular reads, pre-Guppy5 (<20% error)
  --nano-corr path [path ...]
                        ONT reads that were corrected with other methods (<3% error)
  --nano-hq path [path ...]
                        ONT high-quality reads: Guppy5+ SUP or Q20 (<5% error)
  --subassemblies path [path ...]
                        [deprecated] high-quality contigs input
  -g size, --genome-size size
                        estimated genome size (for example, 5m or 2.6g)
  -o path, --out-dir path
                        Output directory
  -t int, --threads int
                        number of parallel threads [1]
  -i int, --iterations int
                        number of polishing iterations [1]
  -m int, --min-overlap int
                        minimum overlap between reads [auto]
  --asm-coverage int    reduced coverage for initial disjointig assembly [not set]
  --hifi-error float    [deprecated] same as --read-error
  --read-error float    adjust parameters for given read error rate (as fraction e.g. 0.03)
  --extra-params extra_params
                        extra configuration parameters list (comma-separated)
  --plasmids            unused (retained for backward compatibility)
  --meta                metagenome / uneven coverage mode
  --keep-haplotypes     do not collapse alternative haplotypes
  --no-alt-contigs      do not output contigs representing alternative haplotypes
  --scaffold            enable scaffolding using graph [disabled by default]
  --trestle             [deprecated] enable Trestle [disabled by default]
  --polish-target path  run polisher on the target sequence
  --resume              resume from the last completed stage
  --resume-from stage_name
                        resume from a custom stage
  --stop-after stage_name
                        stop after the specified stage completed
  --debug               enable debug output
  -v, --version         show program's version number and exit
  --deterministic       perform disjointig assembly single-threaded

Input reads can be in FASTA or FASTQ format, uncompressed
or compressed with gz. Currently, PacBio (CLR, HiFi, corrected)
and ONT reads (regular, HQ, corrected) are supported. Expected error rates are
<15% for PB CLR/regular ONT; <5% for ONT HQ, <3% for corrected, and <1% for HiFi. Note that Flye
was primarily developed to run on uncorrected reads. You may specify multiple
files with reads (separated by spaces). Mixing different read
types is not yet supported. The --meta option enables the mode
for metagenome/uneven coverage assembly.

To reduce memory consumption for large genome assemblies,
you can use a subset of the longest reads for initial disjointig
assembly by specifying --asm-coverage and --genome-size options. Typically,
40x coverage is enough to produce good disjointigs.

You can run Flye polisher as a standalone tool using
--polish-target option.
```

```
flye --nano-raw S_ONT_raw_short.fastq --out-dir S_ONT_raw_short
```
### Assembly datasets and anaylsis provided:
Pacbio E. coli three genomes:

| raw reads      | fastqc | flye | quast |
| ----------- | ----------- |-----------|-----------|
| Header      | Title       |
| Paragraph   | Text        |
