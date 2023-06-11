<img src="thumbnail.png" alt="thumbnail" width="900"/>

# NA-CORDEX Data Visualization Cookbook

[![nightly-build](https://github.com/NCAR/na-cordex-viz-cookbook/actions/workflows/nightly-build.yaml/badge.svg)](https://github.com/NCAR/na-cordex-viz-cookbook/actions/workflows/nightly-build.yaml)
[![Binder](http://binder.mypythia.org/badge_logo.svg)](http://binder.mypythia.org/v2/gh/NCAR/na-cordex-viz-cookbook/main?labpath=notebooks)

This Project Pythia Cookbook covers how to load and view data summaries from the NA-CORDEX dataset.  Documentation for the NA-CORDEX dataset can be found here:  https://na-cordex.org/na-cordex-on-aws.html

## Motivation

This cookbook provides useful methods for summarizing data values in large climate datasets.   It clearly shows where data have extreme values and where data are missing; this can be useful for validating that the data were gathered and stored correctly.   While this cookbook is specifically designed to examine any portion of the NA-CORDEX dataset using an intake catalog, the code can be adapted straightforwardly to other datasets that can be loaded via `xarray`.

The main python packages used are `xarray`, `intake-esm`, `dask`, and `matplotlib`.

## Authors

[Brian Bonnlander](@bonnland), [Seth McGinnis](@sethmcg)

### Contributors

<a href="https://github.com/NCAR/na-cordex-viz-cookbook/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=NCAR/na-cordex-viz-cookbook" />
</a>

## Structure

This cookbook is a single notebook broken into several sections.   The first section allows users to tailor the notebook to their chosen computing environment and storage cloud.  Other sections contain code for subsetting and plotting data, obtaining Dask workers, and producing summary plots.

### Select User Options

Users may choose the value of several boolean switches:

* Cloud storage provider (Amazon AWS or NCAR), 
* Whether to truncate the data if running on a resource-limited computer,
* Whether to obtain a Dask cluster from a PBS Scheduler or via the Dask Gateway package.

**Note**: Using the NCAR cloud storage system requires a login account on an NCAR HPC computer.

### Create and Connect to Dask Distributed Cluster

This section shows several possible ways to create and connect to a Dask cluster for processing data in parallel.

The two provided ways include using either a PBS Scheduler or a Dask Gateway.  

### Find and Obtain Data Using an Intake Catalog

This section shows how to interact with an Intake-ESM catalog to find, select, and open datasets via `xarray`.

### Functions for Subsetting and Plotting

This section provides python functions for subsetting and plotting data.   They rely on the `xarray` and `matplotlib` packages, and can be generalized to other climate datasets.

### Produce Diagnostic Plots

This section produces the diagnostic plots.   It shows how to produce timing information and gives options for saving high-resolution images of the resulting plots.

## Running the Notebooks

You can either run the notebook using [Binder](https://mybinder.org/) or on your local machine.

### Running on Binder

The simplest way to interact with a Jupyter Notebook is through
[Binder](https://mybinder.org/), which enables the execution of a
[Jupyter Book](https://jupyterbook.org) in the cloud. The details of how this works are not
important for now. All you need to know is how to launch a Pythia
Cookbooks chapter via Binder. Simply navigate your mouse to
the top right corner of the book chapter you are viewing and click
on the rocket ship icon, (see figure below), and be sure to select
“launch Binder”. After a moment you should be presented with a
notebook that you can interact with. I.e. you’ll be able to execute
and even change the example programs. You’ll see that the code cells
have no output at first, until you execute them by pressing
{kbd}`Shift`\+{kbd}`Enter`. Complete details on how to interact with
a live Jupyter notebook are described in [Getting Started with
Jupyter](https://foundations.projectpythia.org/foundations/getting-started-jupyter.html).

### Running on Your Own Machine

If you are interested in running this material locally on your computer, you will need to follow this workflow:

(Replace "cookbook-example" with the title of your cookbooks)

1. Clone the `https://github.com/NCAR/na-cordex-viz-cookbook` repository:

   ```bash
    git clone https://github.com/NCAR/na-cordex-viz-cookbook.git
   ```

1. Move into the `na-cordex-viz-cookbook` directory
   ```bash
   cd na-cordex-viz-cookbook
   ```
1. Create and activate your conda environment from the `environment.yml` file
   ```bash
   conda env create -f environment.yml
   conda activate na-cordex-viz-cookbook
   ```
   **Note**: If building the environment fails using conda, consider instead installing the `mamba` package and using `mamba env create -f environment.yml`.
   
1. Move into the `notebooks` directory and start up Jupyterlab
   ```bash
   cd notebooks/
   jupyter lab
   ```
