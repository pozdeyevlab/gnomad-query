# gnomad-query
A workflow to download v4 vcf's from gnomAD, parse vcf's for chrom, pos, alt, ref, all AF &amp; AN to across all available ancestries for use in aligning gwas summary files form multiple biobanks.

# Quick Installation
All dependencies for this workflow are included in the conda environment, except bcftools, which will require independent install by users.
```
conda env create -f environment.yml
conda activate gnomad_query
```

# How to Use
1. Build and activate the conda environment via `environment.yml`
2. Fill in the output directory in `config.yaml` (defaults to a directory GNOMAD_REF in working directory)
3. Run snakemake workflow via command below
```
snakemake --cores 5 --configfile config.yaml
```

# Outputs
This workflow creates two sub-directories in the user defined output directory:
1. ref: Contains per chromosome files that include AN & AF results by ancestry
2. flagged: Contains per chromosome files marking which variants are flagged as having an AN less than 50% of total N

