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

## Step 2: Install HPCToolkit profilers using spack

Spack's install command will perform the installation of HPCToolkit and its dependences:
```
spack/bin/spack install hpctoolkit
```

This installation will take some time. Many of the following steps can be completed while the installation proceeds. If you choose to continue while the installation proceeds, create a new shell and navigate to your base directory.

## Step 3: Download HPCToolkit viewers

HPCToolkit's viewing functionality is provided separately from its profiling functionality. It is provided as a pre-compiled binary. To download, run:
```
wget http://hpctoolkit.org/download/hpcviewer/latest/hpcviewer-linux.gtk.x86_64.tgz
```

For this demo, we use the regular viewer. Downloading and using the trace viewer proceeds similarly.

## Step 4: Configure X11 Forwarding

We want to run the visualizing process on the client machine, but have it appear on the screen of our host machine. To do so, we need to use some sort of SSH forwarding. In this step, we configure the easier-to-use but slower X11 forwarding. A latter step will configure the faster but more complicated xpra forwarding.

Enabling X11 forwarding is different based on the OS of your host computer.

### Step 4.macOS: Configure X11 Forwarding

For macOS, we will use XQuartz to enable X11 forwarding. Start by navigating to https://www.xquartz.org and downloading the .dmg file. Once the download is complete, click on the file and follow the instructions to install.

Next, we configure our ssh settings by adding the following line to the file 

### Step 4.windows: Configure X11 Forwarding

TODO: Copy Shreyas' instructions here
