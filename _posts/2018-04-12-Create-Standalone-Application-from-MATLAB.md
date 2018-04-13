---
layout: post
title: "Create Standalone Application from MATLAB for Newbies"
date: 2018-04-12
tags: [MATLAB]
comments: true
---

**OS 1**: MacOS High Sierra

**OS 2**: Ubuntu 16.0 on VirtualBox

**MATLAB version**: R2018a

The [official guide by MathWorks](https://www.mathworks.com/help/compiler/create-and-install-a-standalone-application-from-matlab-code.html) is almost perfect. However, there are certainly some points to be clarified for newbies like me :honeybee:.

## MATLAB Compiler

This is an application (APP) named **application compiler** in MATLAB.

## MATLAB runtime

MATLAB compiler runtime (MCR) contains all the libraries needed to run the standalone APP and thus is required to be installed by end-users without MATLAB. Therefore, MCR will be accompanied with the installer created in this guide.

## Cross-platform is not allowed

We should create the standalone on the same type of operating system (OS) as the target OS to run it. For example, "To create a standalone which can run on a Linux system you would actually need to create the standalone using MATLAB + MATLAB Compiler for Linux on a Linux machine." (from Mathworks Support).

## matlabroot

It's an object in MATLAB, representing the root directory (dir) of MATLAB. You can check it in Command Window of MATLAB: `>> matlabroot`, mine returns `ans = '/Applications/MATLAB_R2018a.app'`.

## Before "enter magicsquare(5)"

Switch to dir of "magicsquare.m", otherwise MATLAB can not call `magicsqaure` function. Go to Command Window of MATLAB: `>> cd /Applications/MATLAB_R2018a.app/extern/examples/compiler`.

## Before "Package"

Recommend to choose "Runtime downloaded from web", thus the distribution file could be pretty small.

## Run the APP on Mac

Go to Terminal, change dir to where this APP is installed. If everything before was done as default, it should be `cd /Applications/magicsquare`. Before running `export DYLD_LIBRARY_PATH=MCR_ROOT/v92/runtime/maci64:MCR_ROOT/v92/sys/os/maci64:MCR_ROOT/v92/bin/maci64`, replace "MCR_ROOT/v92" with the path to where MCR is installed. For me, it is "/Applications/MATLAB/MATLAB_Runtime/v94". "v92" stands for version 9.2, "v94" stands for version 9.4.

## More tricks

    (1) Sometimes running the APP in terminal just prompts errors which we believe should not happen. In this case, don't hesitate to uninstall the standalone application and delete the distribution files. Then restart your Mac and repeat the way from compiling the app to run it.

    (2) Be sure that your MATLAB have installed the toolboxes required to run all the functions in the application. Otherwise, you will get errors when running the app, e.g. "Undefined function or variable 'wavedec3'". This function comes from "Wavelet Toolbox", so go to "MATLAB > Apps > Get more apps > (search) Wavelet Toolbox > install". Then repeat the way from compiling the app to run it.
    
    (3) To build an APP on Linux, install VirtualBox, and install Ubuntu on it. Everything else is very similar, except that the way to run the APP was found different from the offical guide. Go to Terminal, switch to the installation dir, by default, `cd /usr/local/standalone_app_name`, run `./application/run_standalone_app_name.sh MCR_installation_dir [other_arguments_to_the_APP]`.
      -  MCR_installation_dir: No quotation mark. The default installation dir is “/usr/local/MATLAB/MATLAB_Runtime/v94”.
