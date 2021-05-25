# StructurePrototypeAnalysisPackage
Structure Prototype Analysis Package can analyze symmetry and compare similarity of large amount of atomic structures.

## Description:
The structure prototype analysis package (SPAP) can analyze symmetry and compare 
similarity of a large number of atomic structures. Typically, SPAP can 
analyze structures predicted by CALYPSO (www.calypso.cn). We use spglib to 
analyze symmetry. The coordination characterization function (CCF) is used to 
measure structural similarity. We developed a unique and advanced clustering method 
to automatically classify structures into groups. If you use this program and method in your 
research, please read and cite the publication: J. Phys. Condens. Matter 
2017, 29, 165901.

## Author:
Dr. Chuanxun Su  
CAS Key Laboratory of Quantum Information, University of Science and Technology of China  

## Email:
sucx@ustc.edu.cn / suchuanxun@163.cn

## Dependency:
This program uses numpy, spglib, and ase (https://wiki.fysik.dtu.dk/ase/). You could simply install them by one command: `pip install numpy spglib ase`

## Installation:
Use command: `pip install spap`  
Or download the source code and install: `python3 setup.py install`

## Example Command:
You can run the program by the following commands:  
`spap -h` (show help)  
`spap --nc` (analyze symmetry and don't compare similarity)  
```
spap -e 0.5 --cif --nd  
spap -a -t 0.01 --vasp --nc
spap
spap --vasp -d
spap -n 200 --cif --th 0.05 -r 7.0
```

## Run by Script:
You can run SPAP by scripts. SPAP can run at many different modes.
1.  To analyze CALYPSO structure prediction results, set i_mode=1. Run run_spap.py
    in `results` directory generated by CALYPSO. You can find this script in `example` directory.
2.  To calculate symmetry and compare similarity of a set of structures, set
    i_mode=2. Put structure files in `struc` directory. The files should be
    named *.cif, *.vasp (VASP format), or any name and format ase can read
    automatically.
3.  To read and analyze structures optimized by VASP, set i_mode=3. Define
    work_dir. It is the path where you put the optimized structures.
4.  To calculate symmetry and compare similarity of a list of structures, set
    i_mode=4. Assign a list of Atoms objects to structure_list.  

## Output:
I try to organize the output files similar to those generated by cak.py (we actually don't need cak.py). So 
that it's easier for user to get familiar with SPAP. 
The Analysis_Output.dat lists the information about the analyzed structures. 
However we provide more information such as density (total number of atoms divided by volume), formula unit, and 
volume. The distance.dat stores the distances between structures and some other 
attributes. The analyzed_structures.db is in atomic simulation environment (ASE) 
database format for atoms. You can easily read and analyze these structures 
through ASE. You can also add and store properties you are interested in. 
This functionality is very useful for screening out good functional materials. 
SPAP can also write structures in cif and VASP format in dir_* directory. 
Technically speaking, SPAP can easily write any structure format supported by 
ASE.  

## Revision Log:
Project released on GitHub  
August 19, 2019

Program released on the Python Package Index (PyPI)   
December 8, 2019
