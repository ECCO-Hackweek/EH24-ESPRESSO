# Exploring Sensitivity Patterns and Responses in the Southern Ocean (ESPResSO)




## Files and folders in repo

Overview of what is included in this repo:

* **`notebooks/`**
<br> All Jupyter notebooks generated for this project are included here. There are three separate subdirectories, one for each team member and their notebooks.\
* `.gitignore`
<br> This file sets the files that will be globally ignored by `git` for the project. (e.g. you may want git to ignore temporary files or large data files, [read more about ignoring files here](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files))
* `environment.yml`
<br> `conda` environment description needed to run this project.
* `README.md`
<br> Description of the project

# Project Team Members
<div align="center">
<img src="PXL_20241017_155300381.jpg" height="600" alt="ESPResSO Team photo"  /> <br/>
 From left to right: Marie J. Zahn, Noah A. Rosenberg and Odilon J. Houndegnonto. Behind them is Ian G. Fenty.
</div>

## Project Summary
The ESPResSo stands for Exploring Sensitivity Patterns and Responses in the Southern Ocean. We are using the EMU tools to investigate drivers of volume transport in the Drake Passage. This is a well-studied problem that has been investigated using adjoint models (e.g. Mazloff, 2012). Variability in the transport is known to be driven primarily by zonal wind stress along the Antarctic Circumpolar Current (ACC), with responses on time scales of about one month, in addition to wind stress following bathymetric features in and around the ACC region.

Our goal for this week is to replicate previous results using the adjoint from EMU and ensure we can attribute variability in the Drake Passage transport to recognizable patterns of primarily zonal wind stress. 

### Collaborators


| Name | Personal goals | 
| ------------- | ------------- | 
| Marie Zahn|Familiarize myself with EMU tools and interpreting outputs from the adjoit|
| Noah Rosenberg|I would like to get familiar using EMU and its outputs|
| Odilon Houndegnonto| Understand the ECCO environment and its built-in packages for output analysis. Learn the EMU tools and its outputs management|


### The problem

<!--- Provide a few sentences describing the problem are you going to explore. If this is a technical exploration of software or data science methods, explain why this work is important in a broader context and specific applications of this work. --->

Studies (e.g. Mazloff, 2012) have reported the zonal win stress as the main driver of the volume transport variability through the Drake Passage (between the southern still of the Chilli and the Antarctica). In this project, we first explored the EMU tools of Sampling, Adjoint, Convolution and Attribution. Then, we jointly applied Adjoint and Convolutions on SSH at the Drake Passage and compared the output with Attribution results. This work will validate the EMU tools and make sure that it replicates well the known drivers of the volume transport variability at the Drake Passage. For these purpose, we tried to replicate the study of Mazloff, 2012 [here: https://doi.org/10.1175/JCLI-D-11-00030.1].

## Data and Methods

### Data

<!--Briefly describe and provide citations for the data that will be used (size, format, how to access).--->

We used the ECCO Version 4 release 4 (V4r4) ocean model output.The ECCO V4r4 datasets provide global coverage over the period from 1992 to 2018 at daily, monthly, and snapshot (instantaneous) time intervals. In the present project, we used the weekly average for the EMU Adjoint, Sampling and Attributions tools, and monthly average for Convolution tool. The ECCO grid configurations are divided into 13 tiles. In the present work, the Drake Passage includes the tile 12 and 13 (see image below). The ECCO v4r4 dataset can be accessed from PO.DAAC repository [https://ecco.jpl.nasa.gov/drive/] or from the NASA Earth Observation databaes [https://data.nas.nasa.gov/ecco].
<div align="center">
<!--- <a href="https://www.ecco-group.org/analysis-tools.htm"></a> --->
 <img src="https://www.ecco-group.org/images/ecco_tiles.png" height="600"/>
</div>

- ECCO Version 4 Description: Forget, G., J.-M. Campin, P. Heimbach, C. N. Hill, R. M. Ponte, and C. Wunsch, 2015: ECCO version 4: An integrated framework for non-linear inverse modeling and global ocean state estimation. Geoscientific Model Development, 8. https://www.geosci-model-dev.net/8/3071/2015/

### Methods/tools
We utilized [ECCO Modeling Utilities (EMU)](https://ecco.odyseallc.net/docs/01_16_fukumori_emu_ecco_2024_03.pdf) tools to execute this project, following the nicely documented tutorials available [here](https://ecco-hackweek.github.io/ecco-2024/tutorials/EMU_index.html) from this hackweek.

### Approach

We defines $QoI J$ = (SSH @ Southern tip of Chile) - (SSH @ West Antarctic Peninsula) which represents geostrophic transport through Drake Passage ($r$ = 0.78 wrt total transport in v4r4). We ran the adjoint targeting $J$(January 1993) with weekly lags back to January 1992.

## Project Conclusions

EMU tools recover similar large scale features of sensitivity to wind stress forcing compared to those from a high resolution adjoint (Mazloff 2012). We identified bugs in EMU, including issues surrounding running transport masks. Some open questions remaining include: Why does EV increase at lags up to 52 weeks? Why is sensitivity to zonal wind negative?

Our final powerpoint slide can be found here: [FINAL PROJECT SLIDE](https://docs.google.com/presentation/d/1KKr9KIAILeS5JWGuom2XTw4ymFWFC_LilzXHi3rYuZU/edit?usp=sharing)

