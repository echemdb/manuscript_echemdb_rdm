[![DOI](https://zenodo.org/badge/824276671.svg)](https://zenodo.org/doi/10.5281/zenodo.13739617)

# Welcome to manuscript_echemdb_rdm

This repository contains supporting information for the manuscript denoted [echemdb Toolkit - a Lightweight Approach to Getting Data Ready for Data Management Solutions](https://arxiv.org/abs/2409.07083).
The manuscript illustrates how echemdb's toolbox can be used for local research data management.
It provides information on file naming convention (FNC), automatic/programmatic metadata acquisition, and converting data into [frictionless Data Packages](https://datapackage.org/).
Furthermore, the our [unitpackages](https://echemdb.github.io/unitpackage/) API is introduced (based on the [frictionless Python framework](https://framework.frictionlessdata.io/)), which allows creating, interacting, and exploring these Data Packages.

The examples from the manuscript and the usage of our tools for RDM applications are also illustrated in a [specific documentation](https://echemdb.github.io/rawtofigure/intro.html).

## Structure

The doc folder contains two Jupyter notebooks

* [illustrating automatic annotation of metadata with watchdog](./doc/tag_data.ipynb)
* [providing usage examples for the unitpackage API](./doc/unitpackage_demo.ipynb)

and a folder with

* [data used in the notebooks or shown in the manuscript](./doc/data/)
* [metadata templates for the fileobserver](./doc/files/)

## Installation

The required packages can be found in the [environment.yml], which can be installed manually with pip or conda/mamba

```sh
conda env create -f environment.yml
```
