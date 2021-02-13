This repository contains code to perform COMPASS analysis on Intracellular Cytokine Staining data from a convalescent cohort of COVID-19 subjects who were either hospitalized (n=20) or not hospitalized (n=40). See the accompanying paper on medRxiv: [T cell and antibody functional correlates of severe COVID-19](https://www.medrxiv.org/content/10.1101/2020.11.25.20235150v1)   

## Running the analysis  

1. Download the FCS files for [Study SDY1680 from ImmPort](https://www.immport.org/shared/study/SDY1680):  
    - Click on the Download tab  
    - Log into ImmPort  
    - Check the `ResultFiles` box  
    - Click Download. Aspera will be launched. Files for ICS and Surface Marker experiments will be downloaded at the same time. Download will take some time (total of 18.3 GB, which took 2 hrs and 42 min to download)  
    - These steps for downloading from ImmPort are current as of Feb 8, 2021.
2. Clone or download this repository. The code depends on the current directory structure. Create an R project in this top-level folder. Open it using RStudio. `renv` should launch automatically (see next step).    
3. Install dependencies.  
    - If you use R 4.0 or above or you use recent versions of `openCyto` packages (see below), you may want to check out the `R_v4.0.3` branch.  
    - Analysis for the manuscript was completed using R version 3.6.3 on a computer running Ubuntu 18.04. The code in this branch works with `openCyto` 1.24.0, `CytoML` 1.12.1, `flowCore` 1.52.1, and `flowWorkspace` 3.34.1. Dependencies are listed in the `renv.lock` file. Suggested workflow is to install `renv` and then run `renv::activate()` and `renv::restore()` to install dependencies into this project's `renv` subfolder (see [Collaborating with renv](https://rstudio.github.io/renv/articles/collaborating.html)), though you can install dependencies however way you prefer.  
4. Run `scripts/00_20210208_Copy_and_Rename_ICS_ImmPort_FCS_Files.R` after modifying the variable `ImmPort_dl_path`.  
5. Run the rest of the R and Rmd scripts in numerical order. Output will get placed into the `out` and `processed_data` subfolders (you may want to copy the current output folders somewhere to have an original copy).   
