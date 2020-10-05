This repository contains instructions and example data for installing and using HPCToolkit. The in person demo is scheduled for 10.9.2020

# Overview

HPCToolkit is a suite of applications for profiling and visualizing the performance of programs. It contains both static and dynamic analyses.
Once a program has been analysed, the hpctoolkit viewers are used to visualize the gathered information.

For this demo, we assume the profiling is occuring on a non-local machine over SSH. Thus, this demo includes instructions for forwarding the visualizer to your host machine over SSH.

## Step 0: Select base directory

This tutorial installs new files on your computer. The first step is to decide where those files are going to go. An easy choice for the base directory is the home directory. It is *not* recommended to use this directory as your base directory. We will refer to this directory as `$BASE` for the remainder of this tutorial. We will refer to the directory containing this README as `$DEMO` for the remainder of this tutorial.

We run two commands to prepare our shell for this tutorial/demo. From the directory containing this README, run:
```
export DEMO=$(pwd)
```
Then, navigate to your selected base directory. From that directory, run:
```
export BASE=$(pwd)
```

## Step 1: Install spack

Spack is a package manager that we will use to install HPCToolkit and its dependences. From your base directory, run the following command to download spack:
```
git clone https://github.com/spack/spack.git
```

Spack comes with a premade binary, so the installation process is complete.

## Step 2: Install HPCToolkit using spack

Spack's install command will perform the installation of HPCToolkit and its dependences:
```
spack/bin/spack install hpctoolkit
```

This installation will take some time. Many of the following steps can be completed while the installation proceeds. If you choose to continue while the installation proceeds, create a new shell and navigate to your base directory.

## Step 3: 

## Step 3: 
