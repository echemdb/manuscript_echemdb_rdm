# Welcome to manuscript_echemdb_rdm

This repository contains supporting information for the manuscript [to be submitted].
The manuscript illustrates how echemdb's toolbox can be used for local research data management.
It provides information on file naming convention (FNC) and automatic/programmatic metadata acquisition.
Furthermore, the [unitpackages](https://echemdb.github.io/unitpackage/) API is introduced, which allows creating, interacting, and exploring frictionless datapackages.

The examples from the manuscript and the usage of our tools for RDM applications are also illustrated in a [specific documentation](https://echemdb.github.io/rawtofigure/intro.html).

## Structure

The doc folder contains two Jupyter notebooks

* [illustrating automatic annotation of metadata with watchdog](./doc/tag_data.ipynb)
* [providing usage exampels for the unitpackage API](./doc/unitpackage_demo.ipynb)

and a folder with

* [data used in the notebooks or shown in the manuscript](./doc/data/)
* [metadata templates for the fileobserver](./doc/files/)

## Installation

The required packages can be found in the [environment.yml], which can be installed manually with pip or conda/mamba

```sh
conda env create -f environment.yml
```
