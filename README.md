# This modified version of mutyper adds utilities for characterizing rare somatic mutations to the CLI. 

### install:
pip install git+https://github.com/dustin-mullaney/mutyper_rare_variant

### Usage:
`mutyper_rare_variant` was designed to work with bcf/vcf files generated with `bcftools` multialleic caller. It requires the AD and DP format fields. 
Before running `mutyper_rare_variant` you should standard your vcf/bcf to biallelic format using `bcftools norm`.
Example:

	bcftools mpileup --annotate "FORMAT/AD,FORMAT/DP" -b "${BAM_LIST}" -f "${GENOME}" | bcftools call --thread 8 -mA -Ob -o "${OUT_FILE}"
	bcftools norm -m - "${OUT_FILE}" -Ob -o temp.bcf && mv temp.bcf "${OUT_FILE}"
	
## Utilities and example usage:

### `mutyper spectra` with `--rare`

### `sample_allele_freq()`

---

![](docs/_static/logo.png)

A Python package and command line utility for annotating the local ancestral sequence context of biallelic SNPs

[![Build and test](https://github.com/harrispopgen/mutyper/actions/workflows/build-and-test.yml/badge.svg)](https://github.com/harrispopgen/mutyper/actions/workflows/build-and-test.yml)
[![Docs build and deploy](https://github.com/harrispopgen/mutyper/actions/workflows/docs-build-and-deploy.yml/badge.svg)](https://github.com/harrispopgen/mutyper/actions/workflows/docs-build-and-deploy.yml)
[![Python package](https://github.com/harrispopgen/mutyper/actions/workflows/python-publish.yml/badge.svg)](https://github.com/harrispopgen/mutyper/actions/workflows/python-publish.yml)
[![DOI](https://joss.theoj.org/papers/10.21105/joss.05227/status.svg)](https://doi.org/10.21105/joss.05227)

#### See [documentation](https://harrispopgen.github.io/mutyper) for install and usage information.

Pairs well with the package [`mushi`](https://github.com/harrispopgen/mushi), which performs mutation spectrum history inference.
