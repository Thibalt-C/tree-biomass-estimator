# tree-biomass-estimator

## Preamble

This model has been implemented in an environment where only terrestrial laser scanner (TLS) has been used to scan a forest. More details are available on the "report.pdf" file, giving the detailed procedure. All scripts are accessible under CC licence, feel free to re-use it for your own projects.

## Required software

This model has been tested on MacOS 13.2.1 / Windows 10 Pro Version 22H2. Both hardwares were working with 64-bit-based processors. \
Python scripts have been built using Jupyter Notebook 6.5.4 / JupyterLab 3.3.2, via Anaconda 2.4.2 / 2.4.0. The environment is using a Python 3.8.16 / Python 3.9.16 kernel, and the following packages are used in the scripts:
- numpy
- matplotlib.pyplot 
- laspy
- scikit-learn
- pytorch
- lightning
- hdbscan (facultative)
- time (facultative)
- open3d (facultative)

The following softwares have been used:

- Anaconda 2.4.2
- CloudCompare 2.12
- 3D Forest 0.51
- GeoSLAM Hub 6.2.1 (for acquiring TLS data)


# Methodology

## 1 – Acquisition, subsampling and intensity-based filtering

## 2 – Ground / Tree separation using CANUPO plugin (CloudCompare)

## 3 – Trunk-level clustering using DBSCAN, and deep-learning-based region growing (DLBRG)
