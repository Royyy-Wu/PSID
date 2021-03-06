# PSID: Preferential subspace identification

Given signals y_t (e.g. neural signals) and z_t (e.g behavior), PSID learns a dynamic model for y_t while prioritizing the dynamics that are relevant to z_t. 

For the derivation and results in real neural data see:

Omid G. Sani, Bijan Pesaran, Maryam M. Shanechi  (2019). *Modeling behaviorally relevant neural dynamics using Preferential Subspace IDentification (PSID)* bioRxiv 808154, doi: 10.1101/808154, https://doi.org/10.1101/808154


# Usage guide
## Initialization
Add the source directory and its subdirectories to the path. You can run init.m to do this.

## Main learning function
The main function for the MATLAB implementation is [source/PSID.m](source/PSID.m). A complete usage guide is available in the function. The following shows an example case:
```
idSys = PSID(y, z, nx, n1, i);
```
Inputs:
- y and z are time x dimension matrices with neural (e.g. LFP signal powers or spike counts) and behavioral data (e.g. joint angles, hand position, etc), respectively. 
- nx is the total number of latent states to be identified.
- n1 is the number of states that are going to be dedicated to behaviorally relevant dynamics.
- i is the subspace horizon used for modeling. 

Output:
- idSys: a structure containing all model parameters (A, Cy, Cz, etc). For a full list see the code.

# Example script
Example simulated data and the script for running PSID on the data is provided in 
[example/example.m](example/example.m)
This script perform PSID model identification and visualizes the learned eigenvalues similar to in Supplementary Fig 2.

# Licence
Copyright (c) 2020 University of Southern California  
See full notice in [LICENSE.md](LICENSE.md)  
Omid G. Sani and Maryam M. Shanechi  
Shanechi Lab, University of Southern California
