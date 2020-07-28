# DCPROGS
The goal of DCPROGS is to provide a collection of tools for scientific research on ion channels. The backbone of the package is [DCPROGS suite] (http://www.ucl.ac.uk/Pharmacology/dcpr95.html) written mainly by [Professor David Colquhoun] (http://www.ucl.ac.uk/Pharmacology/dc.html) over the last 40 years. The original programs have been writen in 32 bit FORTRAN90, with some assembler subroutines for fast graphics, and the GINO graphics library and are available to run in DOS. Compiled DOS programs can be downloaded from [DCPROGS/DCDOS] (https://github.com/DCPROGS/DCDOS) repository. See in DCDOS repository for description of DOS programs. Some of the programs have been converted for Microsoft Windows in 32 bit Intel Visual Fortran with Gino Windows graphics. Compiled Windows programs can be downloaded from [DCPROGS/DCWIN] (https://github.com/DCPROGS/DCWIN) repository. The FORTRAN source code is kept in [DCPROGS/DCFORTRAN] (https://github.com/DCPROGS/DCFORTRAN) repository. For more details on FORTRAN DCprogs see [OneMol.org page] (http://www.onemol.org.uk/?page_id=331).

Currently work is in progress to write  some programs in pure Python or Python/C++. The rationale is to preserve and cultivate these tools for future research applications. Below folows brief description of repositories which a currently under development.

### SCALCS
[SCALCS] (https://github.com/DCPROGS/SCALCS) repository contains Python modules and scripts to do various calculations for macroscopic and single channel behaviour, based on Colquhoun & Hawkes equations (see References in SCALCS). Kinetic mechanism can be specified or loaded via DCPYPS modules.

The original DCProgs (FORTRAN) included five separate programes:  SCALCS- calculates the macroscopic response to jumps or pulses in agonist concentration and also equilibrium and peak concentration response curves; SCBST- calculates properties of bursts of openings (as in Colquhoun & Hawkes, 1982); SCJUMP- calculates properties of single channel elicited by a concentration jump (as in Colquhoun et al. , 1997); SCSIM- calculates a simulated series of openings and shuttings; SCCOR- calculate properties of correlations between open times, shut times, burst lengths, openings within a burst etc. (see Colquhoun & Hawkes, 1987). These programs do not allow for missed events. To calculate the distributions of apparent open and shut times, correlations and dependency plots with exact allowance for missed events, the mechanism and rate constants can be loaded into HJCFIT. 

### CVFIT
[CVFIT] (https://github.com/DCPROGS/CVFIT) is a pure Python program for weighted least-squares fitting of various equations to experimental data, for calculating errors of fitting estimates and for plotting the results. Currently only fit with the linear and Hill/Langmuire equations available. 

### HJCFIT
[HJCFIT] (https://github.com/DCPROGS/HJCFIT) repository is an on-going effort by UCL [Research Software Development Team] (https://www.ucl.ac.uk/research-it-services/about/research-software-development) (RSDT) to convert legacy FORTRAN code into a C++11 library.  The core kernel of HJCFIT is a modern C++11 program to compute the likelihood that a given ionic-channel kinetic mechanism reproduces a series of experimentally observed shut and open times while accounting for the missed events (with exact missed events correction).

The project is version controlled, documented, and extensively unit-tested. It is configured and built using CMake. The C++ unit-tests are written using the Google Test framework. It also contains Python bindings, for easy integration within the rest of the DCPROGS software suite. The bindings are built using SWIG, and tested using the Python BDD (behaviour driven development) platform behave. A fairly extensive documentation and API manual is generated via a combination of Sphinx (for Python) and Doxygen (C++) using Breathe.

### DCPYPS
[DCPYPS] (https://github.com/DCPROGS/DCPYPS) is a collection of modules and scripts common to all the DCPROGS repositories. DCPYPS deals with file input/output, specifying kinetic mechanism, creating data structures. SCALCS and HJCFIT depend on DCPYPS.

### DCQTGUI
[DCQTGUI] (https://github.com/DCPROGS/DCQTGUI) repository provides primitive Qt based GUIs for Python based programs.


For more information or questons about DCPROGS contact Remigijus Lape: remis.lp@gmail.com
