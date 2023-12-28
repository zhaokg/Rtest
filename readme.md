##    Installation for Matlab or Octave:
 
>  Method 1: Manually copy all the files in this folder (e.g, beast.m and testdata) to your local folder
            Then, add your local folder to Matlab's search path by running:
```
   addpath( genpath('c:\beast') )   % Replcae c:\beast with your own drive     
```

> Method 2: (Recommendded) The easiest way to install is to simply run the following line of command in Matlab's console:

 ```
   % install to a temp folder
   eval(webread('http://b.link/rbeast',weboptions('cert','')))  

   % Or install it to a chosen folder by first setting the beastPath variable
   beastPath='c:\beast'
   eval(webread('http://b.link/rbeast',weboptions('cert',''))) % install to the folder specified by beastPath
```

   
##    Uninstall

> METHOD 1: Simply delete all the downloaded files manually

> METHOD 2: Automatically remove the files by running:
```           
    rbeast_uninstall
```
 
##      Usage and example
 
#### Major functions available:

* beast:            handle a single regular time series
* beast_irreg:      handle a single irregular time series
* beast123:         handle one or more time seires or stacked images 
* rbeast_uninstall: remove the installed files from the harddisk
* rbeast_update:    check github and update to the latest BEAST version\n");

#### Examples
```
    load('Nile.mat')             % Nile river annual streamflow: trend-only data
    o=beast(Nile, 'start', 1871, 'season','none') 
    printbeast(o))
    plotbeast(o))
```

#### Run 'help beast', 'help beast123', or 'help beast_irreg' for usage and examples        


##    Compilation of the mex file from the C/C++ source files

The BEAST program includes a Matlab mex library compiled from the C soure code (e.g., Rbeast.mexw64 for Windows, Rbeast.mexa64 for Linux, Rbeast.mexmaci64 for MacOS) 
and some Matlab wrapper functions (e.g.,beast.m, and beast123.m) similar to the R interface, as well as some test datasets (e.g., Nile.mat, and co2.mat).

We generated the Matlab mex binary library on our own machines with Win10, Ubuntu 22.04, and macOS High Sierra 10.13. If they fail on your machine, the mex library can
be compiled from the C source code files under Rbeast\Source. If needed, we are happy to work with you to compile for your specific OS or machines. Additional information
on compilations from the C source is also given below.
