# CoastSeg
[![image](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/2320sharon/CoastSeg/blob/main/coastseg_for_google_colab.ipynb)

[![image](https://img.shields.io/pypi/v/coastseg.svg?color=%23ec3dc8)](https://pypi.python.org/pypi/coastseg)
[![image](https://pepy.tech/badge/coastseg)](https://pepy.tech/project/coastseg)
</br>
[![image](https://github.com/SatelliteShorelines/CoastSeg/actions/workflows/pip_install_e.yml/badge.svg)](https://github.com/SatelliteShorelines/CoastSeg/actions)

[![Last Commit](https://img.shields.io/github/last-commit/SatelliteShorelines/CoastSeg)](https://github.com/Doodleverse/segmentation_gym/commits/main)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/SatelliteShorelines/CoastSeg/graphs/commit-activity)
[![Wiki](https://img.shields.io/badge/wiki-documentation-forestgreen)](https://github.com/SatelliteShorelines/CoastSeg/wiki)
![GitHub](https://img.shields.io/github/license/Doodleverse/segmentation_gym)
[![Wiki](https://img.shields.io/badge/discussion-active-forestgreen)](https://github.com/SatelliteShorelines/CoastSeg/discussions)

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white)

![official_coastseg](https://user-images.githubusercontent.com/61564689/212394936-263ec9fc-fb82-45b8-bc79-bc57dafdae73.gif)


## What is CoastSeg?
Coastseg stands for Coastal Segmentation, it is an interactive jupyter notebook for downloading satellite imagery with [CoastSat](https://github.com/kvos/CoastSat) and applying image segmentation models to satellite imagery. CoastSeg provides an interactive interface for drawing Regions of Interest (ROIs) on a map, downloading satellite imagery, loading geojson files, extracting shorelines from satellite imagery, and more.

- A mapping extension for [CoastSat](https://github.com/kvos/CoastSat) using [Segmentation Zoo](https://github.com/Doodleverse/segmentation_zoo) models.
- An interactive interface to download satellite imagery using CoastSat from Google Earth Engine
- An interactive interface for extracting shorelines from satellite imagery
- An interactive interface to apply segmentation models to satellite imagery

![gif of map with rectangles on it](https://github.com/SatelliteShorelines/CoastSeg/blob/main/docs/gifs/create_rois_demo.gif)
- Create ROIs(regions of interest) along the coast and automatically load shorelines on the map.
- Use Google Earth Engine to automatically download satellite imagery for each ROI clicked on the map. 

![gif of map with extracted shorelines on it](https://github.com/SatelliteShorelines/CoastSeg/blob/main/docs/gifs/extract_shorelines_and_transects.gif)
- Coastseg can automatically extract shorelines from downloaded satellite imagery.

## Table of Contents 
- [Quick Start](#quick-start)  
- [Installation Instructions](#installation-instructions)  
- [How to Use CoastSeg](how-to-use-coastSeg)

## Useful Links
- [Wiki](https://github.com/SatelliteShorelines/CoastSeg/wiki)
- [Discussion](https://github.com/SatelliteShorelines/CoastSeg/discussions)
- [Google Colab](https://colab.research.google.com/github/2320sharon/2320sharon/blob/main/coastseg_for_google_colab.ipynb)
- [Contribution Guide](https://github.com/SatelliteShorelines/CoastSeg/wiki/Contribution-Guide)


## Installation Instructions

In order to use Coastseg you need to install Python packages in an environment. We recommend you use [Anaconda](https://www.anaconda.com/products/distribution) to install the python packages in an environment for Coastseg. After you install Anaconda on your PC, open the Anaconda prompt or Terminal in Mac and Linux and use the `cd` command (change directory) to go the folder where you have downloaded the Coastseg repository.

1. Create an Anaconda environment
- This command creates an anaconda environment named `coastseg` and installs `python 3.10` in it.
  ```bash
  conda create --name coastseg python=3.10 -y
  ```

2. Activate your conda environment

   ```bash
   conda activate coastseg
   ```

- If you have successfully activated coastseg you should see that your terminal's command line prompt should now start with `(coastseg)`.

<img src="https://user-images.githubusercontent.com/61564689/184215725-3688aedb-e804-481d-bbb6-8c33b30c4607.png" 
     alt="coastseg activated in anaconda prompt" width="350" height="150">

3. Install Conda Dependencies
   - CoastSeg requires `jupyterlab` and `geopandas` to function properly so they will be installed in the `coastseg` environment.
   - [Geopandas](https://geopandas.org/en/stable/) has [GDAL](https://gdal.org/) as a dependency so its best to install it with conda.
   - Make sure to install geopandas from the `conda-forge` channel to ensure you get the latest version.
   - Make sure to install both jupyterlab and geopandas from the conda forge channel to avoid dependency conflicts
     ```bash
     conda install -c conda-forge geopandas jupyterlab -y
     ```
4. Install the CoastSeg from PyPi
   ```bash
   pip install coastseg
   ```
5. Uninstall the h5py installed by pip and reinstall with conda-forge
   ```bash
   pip uninstall h5py
   conda install -c conda-forge h5py
   ```

## **Having Installation Errors?**

Use the command `conda clean --all` to clean old packages from your anaconda base environment. Ensure you are not in your coastseg environment or any other environment by running `conda deactivate`, to deactivate any environment you're in before running `conda clean --all`. It is recommended that you have Anaconda prompt (terminal for Mac and Linux) open as an administrator before you attempt to install `coastseg` again.

#### Conda Clean Steps

```bash
conda deactivate
conda clean --all
```

# Getting Started

1. Sign up to use Google Earth Engine Python API

First, you need to request access to Google Earth Engine at https://signup.earthengine.google.com/. It takes about 1 day for Google to approve requests.


2. Activate your conda environment

   ```bash
   conda activate coastseg
   ```

- If you have successfully activated coastseg you should see that your terminal's command line prompt should now start with `(coastseg)`.

<img src="https://user-images.githubusercontent.com/61564689/184215725-3688aedb-e804-481d-bbb6-8c33b30c4607.png" 
     alt="coastseg activated in anaconda prompt" width="350" height="150">

3. Download CoastSeg from GitHub

Once you’ve created the coastseg environment you’ll need to run `git clone` the coastseg code onto your computer. Follow the guide [How to Clone CoastSeg](https://github.com/Doodleverse/CoastSeg/wiki/How-to-Clone-Coastseg) in the wiki for how to perform a git clone to download the coastseg code onto your computer.

5. Launch Jupyter Lab

- Run this command in the coastseg directory to launch the notebook `SDS_coastsat_classifier`
   ```bash
   jupyter lab SDS_coastsat_classifier.ipynb
   ```

6. Use the `SDS_coastsat_classifier` to Download Imagery 

Check out the wiki guide  [How to Download Imagery](https://github.com/Doodleverse/CoastSeg/wiki/2.-How-to-Download-Imagery) for comprehensive guides for how to use coastseg to download imagery and apply image segmentation models to the imagery you download. 

## Quick Start for Notebooks
To get started with CoastSeg open this [google colab](https://colab.research.google.com/github/2320sharon/2320sharon/blob/main/coastseg_for_google_colab.ipynb) which will open a jupyter notebook online. The notebook will walk you through connecting to Google Earth Engine, connecting to your google drive so you can save your downloaded images, and using the map dashboard to download satellite imagery.

Alternatively, if you want to get started on your local computer follow the installation instructions, activate the `coastseg` environment, then change to the `CoastSeg` directory `cd coastseg`. Run one of the following notebooks with `jupyter lab` to get started using coastseg. 

**Notebook to Download Satellite Imagery** 
```bash
jupyter lab SDS_coastsat_classifier.ipynb
```

**Notebook to Run Image Segmentation Models**
```bash
jupyter lab SDS_unet_classifier.ipynb
```

# Authors

Package maintainers:

- [@dbuscombe-usgs](https://github.com/dbuscombe-usgs) Marda Science / USGS Pacific Coastal and Marine Science Center.
- [@2320sharon](https://github.com/2320sharon) : Lead Software Developer

Contributions:

- [@ebgoldstein](https://github.com/ebgoldstein)
- [@kvos](https://github.com/kvos)

## Citations
Thank you to all the amazing research who contributed their transects to coastseg.
1. Hawaii small islands https://pubs.usgs.gov/of/2011/1009/data.html
2. Barter Island, Alaska https://www.sciencebase.gov/catalog/item/5fa1f10ad34e198cb793cee4
3. Pacific Northwest, Gulf, and SE USA: Dr Sean Vitousek, USGS-PCMSC, based on DSAS transects
4. Atlantic barrier islands: https://www.sciencebase.gov/catalog/item/5d5ece47e4b01d82ce961e36
5. Mexico, New Zealand, Japan, Chile, Peru all from: https://zenodo.org/record/7758183#.ZCXZMcrMJPY
6. Snyder, A.G., and Gibbs, A.E., 2019, National assessment of shoreline change: A GIS compilation of updated vector shorelines and associated shoreline change data for the north coast of Alaska, Icy Cape to Cape Prince of Wales: U.S. Geological Survey data release, https://doi.org/10.5066/P9H1S1PV.
7. Gibbs, A.E., Ohman, K.A., Coppersmith, R., and Richmond, B.M., 2017, National Assessment of Shoreline Change: A GIS compilation of updated vector shorelines and associated shoreline change data for the north coast of Alaska, U.S. Canadian border to Icy Cape: U.S. Geological Survey data release, https://doi.org/10.5066/F72Z13N1.
8. Himmelstoss, E.A., Kratzmann, M., Hapke, C., Thieler, E.R., and List, J., 2010, The National Assessment of Shoreline Change: A GIS Compilation of Vector Shorelines and Associated Shoreline Change Data for the New England and Mid-Atlantic Coasts: U.S. Geological Survey Open-File Report 2010-1119, available at https://pubs.usgs.gov/of/2010/1119/.
9. Kilian Vos. (2023). Time-series of shoreline change along the Pacific Rim (v1.4) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.7758183
10. Vos, Kilian, Wen, Deng, Harley, Mitchell D., Turner, Ian L., & Splinter, Kristen D. (2022). Beach-face slope dataset for Australia (Version 2) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.7272538
