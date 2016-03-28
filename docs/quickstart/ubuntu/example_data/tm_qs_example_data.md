# First Use of TissueMiner with example data

### 1. Open a terminal

* If you don't know how to open a terminal, click [here](https://help.ubuntu.com/community/UsingTheTerminal)

### 2. Download the example data set (~100 Mb)

Just copy and paste the lines below **into your terminal** and press Enter:
```
     ## In your terminal, type in the command below to download and extract the Demo data
     curl https://cloud.mpi-cbg.de/index.php/s/EspCWSQn3k6NKLA/download  | tar -zxvf -
     
     ## Go to the movie directory
     cd example_movie/demo_ForTissueMiner
```

### 3. Select the analysis you are interested in

Here, we propose some streamlined quickstart tutorials.

* [Cell area](cell_area.md)
* [Cell elongation](cell_elongation.md)
* [Cell packing](cell_packing.md)
* [Cell lineage and divisions](cell_lineage_and_divisions.md)
* [Cell rearrangements](cell_rearrangements.md)
* [Cell contributions to tissue shear](cell_contributions_to_tissue_shear.md)
* [Cell contributions to tissue area changes](cell_contributions_to_tissue_area_changes.md)

All scripts used in these above tutorials can handle user-defined regions of interest (ROI's). Here, we give one example in which multiple ROI's are compared. 

* [Compare cell area in ROI's](cell_area_ROI.md) ***Work in progress...***

### 4. Look at the results 

* Where to find the results ? 

In the current movie folder, a **new output_analysis folder** has been created, where you'll find plots and videos created by running the tutorials. 

* Where to find the current movie folder?

In this tutorial, the example data have been downloaded into your home directory, which may be represented with a "house" icon when using a file browser. In your file browser, go the your home directory, then click on *example_data*, click on *demo_ForTissueMiner*, and finally on *output_analysis*. Here, are your results !
