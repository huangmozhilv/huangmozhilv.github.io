---
layout: post
title: "Create Standalone Application from MATLAB for newbies"
date: 2018-04-12
---

**My platform: macOS High Sierra**


**MATLAB version: R2018a**


The [official guide by MathWorks](https://www.mathworks.com/help/compiler/create-and-install-a-standalone-application-from-matlab-code.html) is almost perfect. However, there are certainly some points to be clarified for newbies like me :honeybee:.

1. MATLAB Compiler is an app named **application compiler** in MATLAB.

2. End-users without MatLab have to install **MATLAB runtime** to run the standalone application. That's why **MATLAB runtime** is accompied with the installer.

3. **Cross-platform is not allowed**. To create a standalone which can run on a certain system we should create the standalone on the same type of operating system (OS). For example, "Also to be able to create a standalone which can run on a Linux system you would actually need to create the standalone using MATLAB + MATLAB Compiler for Linux on a Linux machine." (from Mathworks Support).

4. **"matlabroot"**: it's an object in MATLAB, representing the root directory (dir) of MATLAB. You can check it in Command Window of MATLAB: `>> matlabroot`, mine returns `ans = '/Applications/MATLAB_R2018a.app' `.

5. **Before "enter magicsquare(5)"**, you need to switch to dir of "magicsquare.m", otherwise MATLAB can not call function magicsqaure. Go to Command Window of MATLAB: `>> cd /Applications/MATLAB_R2018a.app/extern/examples/compiler`.

6. **Before "Package"**, recommend to choose "Runtime downloaded from web", thus the distribution file could be rather small.

7. To **run the standalone application** on Mac OS X, **first**, in the terminal, change dir to the folder where this application is installed. If everything before was done as default, it should be `cd /Applications/magicsquare`. **Second**, run `export DYLD_LIBRARY_PATH=MCR_ROOT/v92/runtime/maci64:MCR_ROOT/v92/sys/os/maci64:MCR_ROOT/v92/bin/maci64`. 

    (1) Assure no illegal signs in the code, especially that no spaces around "="; 

    (2) Replace "MCR_ROOT/v92" with the path to the dir where MATLAB compiler runtime (MCR) is installed. For me, it's "/Applications/MATLAB/MATLAB_Runtime/v94". "v92" stands for version 9.2, "v94" stands for version 9.4.

8. More tricks:

    (1) Sometimes running the application in terminal just throw errors which we believe should not happen. In this case, don't hesitate to uninstall the standalone application and delete the distribution files. Then restart your Mac and repeat the way from compiling this app to run it.

    (2) Be sure that your MATLAB have installed the toolboxes required to run all the functions in the application. Otherwise, you will get errors when running the app, e.g. "Undefined function or variable 'wavedec3'". This function comes from "Wavelet Toolbox", so go to "MATLAB > Apps > Get more apps > (search) Wavelet Toolbox > install". Then repeat the way from compiling this app to run it.
