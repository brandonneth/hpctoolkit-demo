This repository contains instructions and example data for installing and using HPCToolkit. The in person demo is scheduled for 10.9.2020

# Overview

HPCToolkit is a suite of applications for profiling and visualizing the performance of programs. It contains both static and dynamic analyses.
Once a program has been analysed, the hpctoolkit viewers are used to visualize the gathered information.

For this demo, we assume the profiling is occuring on a non-local machine over SSH. Thus, this demo includes instructions for forwarding the visualizer to your host machine over SSH.

## Step 0: Select base directory

This tutorial installs new files on your computer. The first step is to decide where those files are going to go. An easy choice for the base directory is the home directory.

We will refer to this directory as `$BASE` for the remainder of this tutorial.
Once you are located in your selected directory, run the following command to prepare your shell for the rest of the tutorial by binding the directory path to the name `BASE`.
```
export BASE=$(pwd)
```


