
# Cell rearrangement analysis

### 1. Make a video of the cell rearrangement coarse-grained pattern plotted on the tissue

We want to calculate the orientation of cell neighbor changes averaged in each element of a square grid, and we want plot the orientation axes (unit nematics) on the tissue. We need a database, but we also need to run the `tm sm topo_countt1` command, which will take information from the database and detect cell neighbor changes (using a routine that is included in the automated workflow). Of note, the `tm sm topo_countt1` command will also build the database if not yet present. The next command on the right runs the analysis and makes the video we want. It outputs the data in the output_analysis folder within the same movie directory.


* Copy-paste the following commands in the terminal:

```
tm sm topo_countt1; tm cell_neighbor_change_orientation_pattern.R . output_analysis
```

![](cell_rearrangements_files/figure-html/cell_neighbor_change_orientation_pattern-1.png)

[Where to find the results ?](../tm_qs_example_data.md#4-look-at-the-results) **|** 
[Back to tutorial list](../tm_qs_example_data.md#3-select-the-analysis-you-are-interested-in)


### 2. Plot cell neighbor change rate

Now, we want to make a graph that shows the average cell neighbor change rate per cell. The `tm sm topo_countt1` command will detect cell neighbor changes (or return "Nothing to be done" if already computed before). The next command on the right does the plot and saves it in the output_analysis folder within the same movie directory.

* Copy-paste the following commands in the terminal:

```
tm sm topo_countt1; tm cell_neighbor_change_rate.R . output_analysis
```

![](cell_rearrangements_files/figure-html/cell_neighbor_change_rate-1.png)

[Where to find the results ?](../tm_qs_example_data.md#4-look-at-the-results) **|** 
[Back to tutorial list](../tm_qs_example_data.md#3-select-the-analysis-you-are-interested-in)

### 3. Plot average cell neighbor change orientation as a function of time

We now want to plot the average cell neighbor change orientation as a function of time in a circular diagram. The time is color coded.


* Copy-paste the following commands in the terminal:

```
tm sm topo_countt1; tm cell_neighbor_change_orientation.R . output_analysis
```

![](cell_rearrangements_files/figure-html/cell_neighbor_change_orientation-1.png)

[Where to find the results ?](../tm_qs_example_data.md#4-look-at-the-results) **|** 
[Back to tutorial list](../tm_qs_example_data.md#3-select-the-analysis-you-are-interested-in)

### 4. For further details

* compare multiple movies and ROI's, see [TM R User Manual](https://mpicbg-scicomp.github.io/tissue_miner/user_manual/TM_R-UserManual.html#comparing-averaged-quantities-between-movies-and-rois)