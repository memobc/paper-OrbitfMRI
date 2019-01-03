# The Paper

This repository includes scripts and data for the following paper:

**Cooper, R. & Ritchey, M. (pre-print)** (add link to preprint)

# Abstract

(edit)

# Resources

Psychtoolbox task scripts are included in the `task` folder. The stimuli used in the experiment can be obatined from the following links: [objects](https://bradylab.ucsd.edu/stimuli.html), [panorama scenes](http://people.csail.mit.edu/jxiao/SUN360/index.html), and [sounds](https://csea.phhp.ufl.edu/media/iadsmessage.html). 

I have also shared a few key analysis scripts in the `analysis` folder along with some corresponding `data` files and `reports`.

The general flow of the included analysis scripts is as follows:
- Analyze **behavioral data**: `Orbit-fMRI-Behavior_Paper.Rmd`
    - The formatted report `Orbit-fMRI-Behavior_Paper.nb.html` contains all analysis output from behavioral data in `Behavioral_data.csv`.
- Analyze **univariate data**: `Orbit-fMRI-Univariate_Paper.Rmd`. This script analyzes first level betas, reflecting the change in mean ROI activity with increasing memory quality.
    - The analysis output can be found in the report `Orbit-fMRI-Univariate_Paper.nb.html`.
- Analyze **background connectivity data**: 
    - Run the first level analysis using the [CONN toobox](https://sites.google.com/view/conn/): `conn_batch_firstlevel_background.m`. This script requires that all task regressors have already been generated.
    - Analyze the first level connectivity data: `Orbit-fMRI-BackgroundConnectivity_Paper.Rmd`. This script calls functions in `background_functions_paper.R` to format, analyze, and visualize the connectivity matrices at the group level. 
    - The report `Orbit-fMRI-BackgroundConnectivity_Paper.nb.html` shows all code and analysis output, and first level ROIxROI connectivity matrices for encoding and retrieval can be found in `Background_connectivity_data.RData`. 
- Analyze **memory-modulated connectivity (gPPI) data**: 
    - Run the first level analysis using CONN: `conn_batch_firstlevel_memorygPPI.m`. This script requires that all task regressors have already been generated.
    - Analyze the first level connectivity data: `Orbit-fMRI-MemorygPPI_Paper.Rmd`. This script calls functions in `gPPI_functions_paper.R` to format, analyze, and visualize the network and ROI connectivity matrices at the group level.
    - The report `Orbit-fMRI-MemorygPPI_Paper.nb.html` shows all code and analysis output, testing changes in connectivity with i) *overall memory quality*, ii) *color memory precision*, and iii) *scene memory precision*. First level ROIxROI connectivity matrices (beta estimates for the PPI regressor) for each memory modulator can be found in `Memory_gPPI_data.RData`. 
    - The group-level results of the hippocampus seed to voxel analysis (change in whole-brain hippocampal connectivity with increasing memory quality) are also provided as an spmT.nii file: `HippSeed_wholebrain_MemoryQuality_spmT.nii`.

# Comments?

Please direct any comments to Rose Cooper, rose.cooper at bc.edu. Please feel free to use any of these scripts. Unfortunately I cannot provide support for you to adapt them to your own data. Notice a bug? Please tell me.
