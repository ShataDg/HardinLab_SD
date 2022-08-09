# HardinLab
2020 02 06 COBA Embryonic epidermis, Jeff Hardin Lab (UW-Madison) - p_20embryonicepidermis


## Data

This pipeline were developed for 3/4D datasets of C. elegans embryo development. Example images are not avaiable at this moment. 
The FindFocusMacroEdge.ijm is a macro for ImageJ/Fiji to select the in-focus plane of 4D datasets and can be used on brightfield or fluorescent images.
The epidermalcells.zip is the Cellpose model to detect epidermal cells and can be used on CellProfiler (runCellpose module) or on Trackmate, which allows the detection and track of the cells on time-series movies.
The maskextractor.cppipe is a pipeline to extrack mask from annotated RGB images. This masks were used to train the CellPose model.

## Instructions

The pipelines require installing cellprofiler from source and downloading and configuring the cellprofiler-plugins repo. Check out the instructions available [on Github](https://github.com/CellProfiler/CellProfiler-plugins).

To run trackmate cellpose detector it's required to install cellpose software and the cellpose_trackmate plugin in FIJI (https://imagej.net/plugins/trackmate/trackmate-cellpose).

Note: If you don't have a GPU, Cellpose will use the CPU.

## Example results

### Cell segmentation in nomarki images:
![](/images:README/Hardin_2022_Meth_CellBio.png)

### CellProfiler extract masks:
![](/images:README/extract_masks.png)

### Cell segmentation and tracking (Cellpose_trackmate in FIJI):
![](/images:README/celldetection_tracking.png)

