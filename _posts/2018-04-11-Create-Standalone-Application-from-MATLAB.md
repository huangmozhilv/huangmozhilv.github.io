---
layout: post
title: "Create Standalone Application from MATLAB (modified)"
date: 2018-04-11
---
**My platform: macOS High Sierra**
**MATLAB version: R2018a**


The [official guide by MathWorks](https://www.mathworks.com/help/compiler/create-and-install-a-standalone-application-from-matlab-code.html) is almost perfect. However, there are certainly some notes to be clarified for newbies like me :honeybee:.

1. MATLAB Compiler is an app named **application compiler** in MATLAB.

2. **Cross-platform is not allowed**. To create a standalone which can run on a certain system we should create the standalone on the same type of operating system (OS). For example, "Also to be able to create a standalone which can run on a Linux system you would actually need to create the standalone using MATLAB + MATLAB Compiler for Linux on a Linux machine." (from Mathworks Support).

3. **matlabroot**: it's an object in MATLAB, represent the root directory (dir) of MATLAB. You can check it in Command Window of MATLAB.
```
>> matlabroot

  ans =

      '/Applications/MATLAB_R2018a.app'
```

4. Before **enter magicsquare(5)**, you need to switch to dir of "magicsquare.m", otherwise MATLAB can not call function magicsqaure. Go to Command Window of MATLAB:
```
>> cd /Applications/MATLAB_R2018a.app/extern/examples/compiler
```

5. Before **Package**, Recommend to choose "Runtime downloaded from web", thus the distribution file could be rather small.

6. To run the standalone application on Mac OS X, first, in the terminal, change dir to the folder where this application is installed. If everything before was done as default, it should be `cd /Applications/magicsquare`. Second, run `export DYLD_LIBRARY_PATH=MCR_ROOT/v92/runtime/maci64:MCR_ROOT/v92/sys/os/maci64:MCR_ROOT/v92/bin/maci64` 
==**NOTE: Below is the most important**==
⋅⋅* Assure no illegal signs in the code, especially that no spaces around "="; 
⋅⋅* Replace "MCR_ROOT/v92" with the path to the dir where MATLAB compiler runtime (MCR) is installed. For me, it's "/Applications/MATLAB/MATLAB_Runtime/v94". "v92" stands for version 9.2, "v94" stands for version 9.4.
