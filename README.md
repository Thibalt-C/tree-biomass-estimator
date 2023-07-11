# tree-biomass-estimator

## Preamble

This model has been implemented in an environment where only terrestrial laser scanner (TLS) has been used to scan a forest. More details are available on the "report.pdf" file, giving the detailed procedure. All scripts are accessible under CC licence, feel free to re-use it for your own projects.

## Required software

This model has been tested on MacOS 13.2.1 / Windows 10 Pro Version 22H2. Both hardwares were working with 64-bit-based processors. \
Python scripts have been built using Jupyter Notebook 6.5.4 / JupyterLab 3.3.2, via Anaconda 2.4.2 / 2.4.0. The environment is using a Python 3.8.16 / Python 3.9.16 kernel, and the following packages are used in the scripts:
- numpy
- pandas
- matplotlib.pyplot 
- laspy
- scikit-learn
- os (facultative)
- hdbscan (facultative, an equivalent module is implemented in scikit-learn 1.3.0 or more recent release)
- time (facultative)

A facultative module means that the script can work without the code using this module, even though it should be better optimized with these extra lines. For example, os module is used for deleting point clouds previously present in a directory to avoid the mixing of several exporting sequences.

The following softwares have been used:

- Anaconda 2.4 with Python 3.8 or more (3.8 and 3.9 have been tested) and a recent release of Jupyter Notebook or Jupyter Lab
- CloudCompare 2.12
- 3D Forest 0.51
- GeoSLAM Hub 6.2.1 (for acquiring TLS data)

## Rapid use

For a rapid use without detailled steps of the processing, you can use the notebook 'functions.ipynb'. It compiles all of the necessary scripts with conveniences such as the possibility to stop plotting for gaining computational time, or auto-selection of the region of interest.

- Compute **intensity_filter(file,slices,ROI)**: _file_ is the name of the file located in the 1-labelled directory, _slices_ is the number of slices created to compute the intensity filtering, _ROI_ is a list of 4 limits of the region of interest (ROI) on the horizontal plane (x,y), it can be replaced by 'auto' to compute the ROI so that it keeps ~95 % of the points;
- Use **_CloudCompare_** to classify trees and terrain (_CANUPO_ plugin)
- Compute **DBSCAN_clustering(file,ROIzmin,ROIzmax,eps,min_samples)**: _file_ is the name of the file located in the 3-labelled directory, in 'trees', _ROIzmin_ and _ROIzmax_ are the vertical limits of the slice of the ROI used to find clusters, it should be located at trunk level, _eps_ is the maximal space between two core points of a cluster, _min_samples_ is the minimal number of core points recquired to form a cluster;
- Use _**3D Forest**_ to perform segmentation of the same file used in the previous function
- Compute **merging(dist_to_merge,ROIzmin,ROIzmax)**: _dist_to_merge_ is the maximum distance between centroids of clusters obtained from DBSCAN and regions obtained with 3D Forest so that one or several clusters can merge with a region, _ROIzmin_ and _ROIzmax_ have to be the same than in the preivous function;
- Compute **region_growing(ROI_file,max_distance,ROIzmin,ROIzmax)**:
- Compute **nearest_nbr_reinforcement()**:
- Use _**3D Forest**_ to perform single tree analysis and QSM
- Compute **plot_results()**: 

Note that between each step, it is possible to manually edit the point clouds using a cloud editing software like **_CloudCompare_**.
