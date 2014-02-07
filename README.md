QuickPlot
=========

A set of python scripts to make contour plots from 2D XD2006 grd-files.

The script needs libraries, 'xd_grd_lib.py' and 'atom_dictionay.py' that should
be put in the python path or in the same folder as this file. The modules
matplotlib and numpy are also required.
The script has been tested with:
OSX: python:2.7.3, numpy:1.8.0, matplotlib:1.3.1

The script can be run from the command line with no arguments, one argument or 
two arguments:
- 0 args: If 'xd_fou.grd' is found it is plotted using default parameters. A 
    parameter file 'qp.par' is written.
- 1 arg: The first argument is the name of the grd-file to be plotted. The plot
    will be made using default parmetes and a parameter file 'qp.par' is 
    written.
- 2 args: First arg must be the grd-file and the second arg the parameter file 
    to be used.
    
If a 3D file is supplied the program exits.

The parameter file can be edited to change the look of the plots. Remember to
save the file under a new name as the program will overwrite it if no parameter
file is specified.

A file 'change_atom_properties.txt' is written and can be used to configure 
non-standard cavalent radii and atom colors. Do NOT change the name of this 
file, it will not be overwritten.

The arguments can be files in the cwd or the absolute path, i.e. under Linux 
it is possible to make bash functions with different parameter files e.g.:
	function defplot(){
		python /ABSPATH/quickplot.py $1 /ABSPATH/def.par
	}
or alaternatively without arguments:   
	function defplot(){
    		python /ABSPATH/quickplot.py xd_def.grd /ABSPATH/def.par
	}

In Windows it is possible to create a batch file located in the search path. Here is an example (quickplot.bat):
	@echo off
	python C:\QuickPlot\quickplot.py %*
	pause
This will pass optional arguments to python. It is also possible to have 
customized parameter files (def_plot.bat):
	@echo off
	python C:\QuickPlot\quickplot.py %1 C:\QuickPlot\par_files\def.par
	pause

Mads Ry Joergensen, 2014, Aarhus University
