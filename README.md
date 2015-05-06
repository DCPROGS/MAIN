# DCPROGS
The goal of DCPROGS is to provide a collection of tools for scientific research on ion channels. The package is derived from the DCPROGS suite (http://www.ucl.ac.uk/Pharmacology/dcpr95.html) and will consist of a Python port, algorithms writen in C++ and wrap of some Fortran code with ~30 years usage at University College London. The rationale is to preserve and cultivate these tools for future research applications.
# Brief description of hosted repositories
# SCALCS
SCALCS repository contains Python modules and scripts to do various calculations for macroscopic and single channel behaviour, based on Colquhoun & Hawkes equations (see References in SCALCS). Kinetic mechanism can be specified or loaded via DCPYPS modules.

The original DCProgs (FORTRAN) included five separate programes:  SCALCS- calculates the macroscopic response to jumps or pulses in agonist concentration and also equilibrium and peak concentration response curves; SCBST- calculates properties of bursts of openings (as in Colquhoun & Hawkes, 1982); SCJUMP- calculates properties of single channel elicited by a concentration jump (as in Colquhoun et al. , 1997); SCSIM- calculates a simulated series of openings and shuttings; SCCOR- calculate properties of correlations between open times, shut times, burst lengths, openings within a burst etc. (see Colquhoun & Hawkes, 1987). These programs do not allow for missed events. To calculate the distributions of apparent open and shut times, correlations and dependency plots with exact allowance for missed events, the mechanism and rate constants can be loaded into HJCFIT. The binary files of the original SCALCS, SCBST, SCJUMP, SCCOR and SCSIM can be found in SCALCS/legacy/bin.
#CVFIT
CVFIT is a program for weighted least-squares fitting of various equations to experimental data, for calculating errors of fitting estimates and for plotting the results. Currently only fit with the linear and Hill/Langmuire equations available. 
#HJCFIT
HJCFIT is a program for maximum likelihood fitting of a mechanism directly to the entire sequence of open and shut times, with exact missed events correction. The input for HJCFIT is a list of idealised open and shut time intervals. A kinetic mechanism is specified (via DCPYPS) with some initial guesses for the rate constants. Currently fitting is done using the Simplex algorithm to maximise the likelihood.

The name of the program is an acronym for Hawkes, Jalali & Colquhoun, whose papers in 1990 and 1992 (HJC92) described the exact solution of the missed event problem, which is the basis of the program. The HJCFIT method was first described by Colquhoun, Hawkes & Srodzinski in 1996 (CHS96). The properties of the estimates of rate constants obtained by this method have now been evaluated (Colquhoun, Hatton & Hawkes, 2003).

#DCPYPS
DCPYPS is a collection of modules and scripts common to all the DCPROGS repositories. DCPYPS deals with file input/output, specifying kinetic mechanism, creating data structures. SCALCS and HJCFIT depend on DCPYPS.
