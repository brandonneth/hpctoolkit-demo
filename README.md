This repository contains instructions and example data for installing and using HPCToolkit. The in person demo is scheduled for 10.9.2020

# Overview

HPCToolkit is a suite of applications for profiling and visualizing the performance of programs. It contains both static and dynamic analyses.
Once a program has been analysed, the hpctoolkit viewers are used to visualize the gathered information.

For this demo, we assume the profiling is occuring on rose (Dr. Strout's research machine), and the visualization is occuring on rose and being forwarded to your local machine. For forwarding, we will be using xpra.

## Step 1: Update your `PATH` variable to access HPCToolkit binaries

HPCToolkit is installed using spack, and to avoid having each person individually spack install HPCToolkit, we will all use the binaries I have installed.

Copy the following lines and paste them at the end of your ~/.bashrc file.

```
export PATH=$PATH:/home/brandonneth/spack/opt/spack/linux-ubuntu16.04-broadwell/gcc-7.3.0/hpctoolkit-2020.08.03-neqpjnbzhr2eobobptso63rrmor3fpxt/bin/
export PATH=$PATH:/home/brandonneth/hpcviewer
```

Now, after running the command `source ~/.bashrc`, you should be able to use the HPCToolkit commands from anywhere on rose.

## Step 2: Using xpra

We will use xpra to do ssh forwarding because it is much more responsive than X11 forwarding.
Start by installing xpra on your local machine from xpra.org. The server side application is already installed on rose.

To use xpra, there are two parts: server side and client side. On the server side, we will begin the application we want to forward, and then link to that running application from the client side.

To start the application, select a display number. This example will use the number 42, but you will need to select a different number because each number can only be used by one person.

Then, using that number in place of 42, run the following command.

```
xpra start :42 --start="hpcviewer hpctoolkit-lulesh-v2.0-RAJA-seq.exe-database"
```

This will start the xpra server, which we will then connect to from our client machine.
On the client machine, open Xpra and select Connect.
Change 'Mode' to SSH -> SSH. 
Sign into lectura as the proxy server and rose as the server. 
Finally, select Connect.
You should see the hpcviewer window appear.







