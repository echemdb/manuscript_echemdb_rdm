# Getting started

This is a short step by step introduction on how to proceed with the implementation of the local data management approach presented in the article [A Lightweight File System Based Approach to Getting Data Ready for Data Management Solutions](https://arxiv.org/abs/2409.07083).

The files used in this documentation can be found in the repository or on Zenodo at [![DOI](https://zenodo.org/badge/824276671.svg)](https://zenodo.org/doi/10.5281/zenodo.13739617).

The following steps are presented in this documentation

* Software and Installation
* Creation of YAML metadata templates
* Automatic annotation of files in the file system upon their creation
* Creation, loading and exploring of frictionless based Data Packages

## Software and Installation

Some of the tutorial files require Python and Jupyter. There are numerous resources on the web describing how to get started in detail with these tools. In principle you can simply install [Anaconda](https://www.anaconda.com/) and [VSCode](https://code.visualstudio.com/). The first time you run one of the notebooks in this documentation in VSCode, you will be asked to install the `ipykernel` and then you should be ready to go.

Some notebooks require additional modules to be installed. In that case open a terminal (in VSCode select in the top bar `Terminal` -> `New Terminal`) and install the modules simply via (you can also replace `pip` with `conda`)

```sh
pip install watchdog
pip install unitpackage
```

If a module seems missing, proceed in the same way, by providing the missing module name.

## Metadata Templates

To create a simple YAML metadata template, you only need a text editor. Create a folder named `metadata_templates` and create a file named, for example, `template.yaml` (sometimes also the suffix `.yml` is used).
Open the file with a text editor and paste the following information.

```yaml
user: Max Doe
sample name: abc123
experiment: My first demo experiment.
```

Please refer to web resources to learn more about more complex YAML structures, such as [here](https://www.tutorialspoint.com/yaml/index.htm).

In the example above, the content is shown with syntax highlighting. Standard text editors of your operating system might not be shipped with that option. In some cases they can be enhanced with plugins. Otherwise we recommended using alternatives such as [Notepad++](https://notepad-plus-plus.org/) (Windows) or [VSCode](https://code.visualstudio.com/) (Platform independent). The latter comes in handy for the next sections.

## Automatic data annotation

We present two approaches to annotate new files with the above metadata schema.

### autotag-metadata

You can simply use a standalone application named [`autotag-metadata`](https://echemdb.github.io/autotag-metadata/). The installation instructions can be found in the documentation.
In the program select the `template.yaml`, the folder where data will be stored and the suffix that the file will have, i.e., `.txt`.
Upon creating a new file in the folder named `test.txt`, an additional file named `test.txt.meta.yaml` will appear, which contains the content from the metadata template. Adjust the metadata template within `autotag-metadata` slightly and store another file `test2.txt`, which will yield another metadata file, with the updated information.
Run multiple instances of the tagging software to observe multiple folders.

### Custom file observer

The custom Python based file observed can be found [here](tag_data.ipynb).
Executing the notebook requires Python, Jupyter, and the `watchdog` module, whose installation instructions were provided above. The watchdog version used was `watchdog>=4,<5`.

## Data Packages

Considering that the tagged files above are CSV files, we can create frictionless based Data Packages with the `unitpackage` module (tested with version `>=0.8.4,<0.9.0`). Conversion of other files was not supported to that point (keep an eye on the [`unitpackage` Changelog](https://github.com/echemdb/unitpackage/blob/main/ChangeLog) or refer to the [frictionless framework](https://framework.frictionlessdata.io/) documentation for custom implementations).

The short introduction into `unitpackage` related to the manuscript can be found [here](unitpackage_demo.ipynb). For more extensive information the reader is referred to the [`unitpackage` documentation](https://echemdb.github.io/unitpackage/).
