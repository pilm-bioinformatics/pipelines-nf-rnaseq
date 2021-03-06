# nf-core/rnaseq: Changelog

## Version 1.4dev

### Pipeline updates

* Added tximport to merge salmon output
* Added Salmon as an supplementary method to STAR and HiSAT2
* Added `--psuedo_aligner`, `--transcript_fasta` and `--salmon_index` parameters
* Add `Citation` and `Quick Start` section to `README.md`
* Integrate changes in `nf-core/tools v1.6` template
* Add tximport and summarizedexperiment dependency [#171](https://github.com/nf-core/rnaseq/issues/171)
* Change all boolean parameters from snake_case to camelCase and vice versa for value parameters
* Appointed changes because of missing output of the multiqc_plots folder [#200](https://github.com/nf-core/rnaseq/issues/200)
* Add Qualimap dependency [#202](https://github.com/nf-core/rnaseq/issues/202)
* Add Qualimap [#202](https://github.com/nf-core/rnaseq/issues/202)
* Obtain edgeR + dupRadar version information [#198](https://github.com/nf-core/rnaseq/issues/198) and [#112](https://github.com/nf-core/rnaseq/issues/112)
* Get MultiQC to save plots as [standalone files](https://github.com/nf-core/rnaseq/issues/183)
* Get MultiQC to save plots as [standalone files](https://github.com/nf-core/rnaseq/issues/183): added the folder "multiqc_plots" to the output.
* Get MultiQC to write out the software versions in a .csv file [#185](https://github.com/nf-core/rnaseq/issues/185)

### Dependency Updates

* Picard 2.20.0 -> 2.20.2
* bioconductor-dupradar 1.12.1 -> 1.14.0
* bioconductor-edger 3.24.3 -> 3.26.0
* csvtk 0.17.0 -> 0.18.2
* gffread 0.9.12 -> 0.11.4
* qualimap 2.2.2b -> 2.2.2c
* trim-galore 0.6.1 -> 0.6.2
* gffread 0.9.12 -> 0.11.4
* Force matplotlib=3.0.3
* Added Salmon 0.14.0
* Added RSEM 1.3.2
* Added tximport 1.0.3
* Added SummarizedExperiment 1.12.0

## [Version 1.3](https://github.com/nf-core/rnaseq/releases/tag/1.3) - 2019-03-26

### Pipeline Updates

* Added configurable options to specify group attributes for featureCounts [#144](https://github.com/nf-core/rnaseq/issues/144)
* Added support for RSeqC 3.0 [#148](https://github.com/nf-core/rnaseq/issues/148)
* Added a `parameters.settings.json` file for use with the new `nf-core launch` helper tool.
* Centralized all configuration profiles using [nf-core/configs](https://github.com/nf-core/configs)
* Fixed all centralized configs [for offline usage](https://github.com/nf-core/rnaseq/issues/163)
* Hide %dup in [multiqc report](https://github.com/nf-core/rnaseq/issues/150)
* Add option for Trimming NextSeq data properly ([@jburos work](https://github.com/jburos))

### Bug fixes

* Fixing HISAT2 Index Building for large reference genomes [#153](https://github.com/nf-core/rnaseq/issues/153)
* Fixing HISAT2 BAM sorting using more memory than available on the system
* Fixing MarkDuplicates memory consumption issues following [#179](https://github.com/nf-core/rnaseq/pull/179)

### Dependency Updates

* RSeQC 2.6.4 -> 3.0.0
* Picard 2.18.15 -> 2.20.0
* r-data.table 1.11.4 -> 1.12.2
* bioconductor-edger 3.24.1 -> 3.24.3
* r-markdown 0.8 -> 0.9
* csvtk 0.15.0 -> 0.17.0
* stringtie 1.3.4 -> 1.3.6
* subread 1.6.2 -> 1.6.4
* gffread 0.9.9 -> 0.9.12
* multiqc 1.6 -> 1.7
* deeptools 3.2.0 -> 3.2.1
* trim-galore 0.5.0 -> 0.6.1
* qualimap 2.2.2b
* matplotlib 3.0.3
* r-base 3.5.1

## [Version 1.2](https://github.com/nf-core/rnaseq/releases/tag/1.2) - 2018-12-12

### Pipeline updates

* Removed some outdated documentation about non-existent features
* Config refactoring and code cleaning
* Added a `--fcExtraAttributes` option to specify more than ENSEMBL gene names in `featureCounts`
* Remove legacy rseqc `strandRule` config code. [#119](https://github.com/nf-core/rnaseq/issues/119)
* Added STRINGTIE ballgown output to results folder [#125](https://github.com/nf-core/rnaseq/issues/125)
* HiSAT index build now requests `200GB` memory, enough to use the exons / splice junction option for building.
  * Added documentation about the `--hisatBuildMemory` option.
* BAM indices are stored and re-used between processes [#71](https://github.com/nf-core/rnaseq/issues/71)

### Bug Fixes

* Fixed conda bug which caused problems with environment resolution due to changes in bioconda [#113](https://github.com/nf-core/rnaseq/issues/113)
* Fixed wrong gffread command line [#117](https://github.com/nf-core/rnaseq/issues/117)
* Added `cpus = 1` to `workflow summary process` [#130](https://github.com/nf-core/rnaseq/issues/130)

## [Version 1.1](https://github.com/nf-core/rnaseq/releases/tag/1.1) - 2018-10-05

### Pipeline updates

* Wrote docs and made minor tweaks to the `--skip_qc` and associated options
* Removed the depreciated `uppmax-modules` config profile
* Updated the `hebbe` config profile to use the new `withName` syntax too
* Use new `workflow.manifest` variables in the pipeline script
* Updated minimum nextflow version to `0.32.0`

### Bug Fixes

* [#77](https://github.com/nf-core/rnaseq/issues/77): Added back `executor = 'local'` for the `workflow_summary_mqc`
* [#95](https://github.com/nf-core/rnaseq/issues/95): Check if task.memory is false instead of null
* [#97](https://github.com/nf-core/rnaseq/issues/97): Resolved edge-case where numeric sample IDs are parsed as numbers causing some samples to be incorrectly overwritten.

## [Version 1.0](https://github.com/nf-core/rnaseq/releases/tag/1.0) - 2018-08-20

This release marks the point where the pipeline was moved from [SciLifeLab/NGI-RNAseq](https://github.com/SciLifeLab/NGI-RNAseq)
over to the new [nf-core](http://nf-co.re/) community, at [nf-core/rnaseq](https://github.com/nf-core/rnaseq).

View the previous changelog at [SciLifeLab/NGI-RNAseq/CHANGELOG.md](https://github.com/SciLifeLab/NGI-RNAseq/blob/master/CHANGELOG.md)

In addition to porting to the new nf-core community, the pipeline has had a number of major changes in this version.
There have been 157 commits by 16 different contributors covering 70 different files in the pipeline: 7,357 additions and 8,236 deletions!

In summary, the main changes are:

* Rebranding and renaming throughout the pipeline to nf-core
* Updating many parts of the pipeline config and style to meet nf-core standards
* Support for GFF files in addition to GTF files
  * Just use `--gff` instead of `--gtf` when specifying a file path
* New command line options to skip various quality control steps
* More safety checks when launching a pipeline
  * Several new sanity checks - for example, that the specified reference genome exists
* Improved performance with memory usage (especially STAR and Picard)
* New BigWig file outputs for plotting coverage across the genome
* Refactored gene body coverage calculation, now much faster and using much less memory
* Bugfixes in the MultiQC process to avoid edge cases where it wouldn't run
* MultiQC report now automatically attached to the email sent when the pipeline completes
* New testing method, with data on GitHub
  * Now run pipeline with `-profile test` instead of using bash scripts
* Rewritten continuous integration tests with Travis CI
* New explicit support for Singularity containers
* Improved MultiQC support for DupRadar and featureCounts
  * Now works for all users instead of just NGI Stockholm
* New configuration for use on AWS batch
* Updated config syntax to support latest versions of Nextflow
* Built-in support for a number of new local HPC systems
  * CCGA, GIS, UCT HEX, updates to UPPMAX, CFC, BINAC, Hebbe, c3se
* Slightly improved documentation (more updates to come)
* Updated software packages

...and many more minor tweaks.

Thanks to everyone who has worked on this release!
