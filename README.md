# pABC-SMC

Table of Content:

1. [pABC-SMC Scripts](#pabc-smc-scripts)
  * **MISSING**
2. [Tumor Growth Simulation Tool](#tumor-growth-simulation-tool)
  * [Compilation & Installation](#compiling--installation)
  * [Usage](#usage)
    * [Tumor Simulation](#1-tumor-simulation)
    * [Comparison with Data](#2-comparison-with-data)
3. [Example Data](#example-data)


## pABC-SMC Scripts

**MISSING**

## Tumor Growth Simulation Tool
### Compiling & Installation
No prerequisites are needed for compilation, except `autotools`, `make` and `g++`. 


To configure and compile the code on your system just execute: 
```
autoreconf
./configure
make
sudo make install
``` 

If everything worked properly, the following files will have been installed:

* Library:
  libnix
  
* Executables:
  nix-tumor2d
  nix-tumor3d
  nix-compare2d
  nix-compare3d
  

### Usage 
####1) Tumor Simulation:
For a simple tumor growth simulation of **1 realisation** for **200 hours** on a **two-dimensional lattice** execute:

```
nix-tumor2d -x 1 -y 200
```

The equivalent in **three dimensions** and a batch of **20 realisations**:

```
nix-tumor3d -x 1 -y 200
```

The default model parameter values can be modified by passing further arguments:

######Table 1: Model Parameters
| Argument | Description | Default Value |
| --- | --- | --- |
| `-Rdiv FLOAT` | division rate (1/hours) | 0.032 |
| `-RReentranceProbabilityLength FLOAT` | division depth (\mu m) | 130 |
| `-RInitialRadius FLOAT` | initial tumor radius (\mu m) | 1 |
| `-RInitialQuiescentFraction FLOAT` | initial quiescent cell fraction (-) | 0.032 |
| `-RECMProductionRate FLOAT` | ECM production rate (1/hours) | 0.032 |
| `-RECMDegradationRate FLOAT` | ECM degradation rate (1/hours) | 0.032 |
| `-RECMThresholdQuiescence FLOAT` | ECM division threshold (-) | 0.032 |
| `-Rre FLOAT` | cell cycle reentrance rate (1/hours) | 0.032 |
| `-Rnec FLOAT` | necrosis rate (1/hours) | 0.032 |
| `-Rlys FLOAT` | lysis rate (1/hours) | 0.032 |
| `-RATPThresholdQuiescence FLOAT` | ATP synthesis division threshold (mM/h) | 0.032 |
| `-RATPThresholdDeath FLOAT` | ATP synthesis necrosis threshold (mM/h) | 0.032 |
| `-RLactateThresholdQuiescence FLOAT` | lactate division threshold (mM) | 0.032 |
| `-RLactateThresholdDeath FLOAT` | lactate necrosis threshold (mM) | 0.032 |
| `-RWasteDiffusion FLOAT` | waste diffusion coefficient (\mu m^2/hours) | 0.032 |
| `-RWasteUptake FLOAT` | waste degradation rate (1/hours) | 0.032 |
| `-RWasteThresholdSlowedGrowth FLOAT` | waste division threshold (mM) | 0.032 |
| `-RWasteIntoxicatedCellCycles FLOAT` | maximum number of cell cycles under waste exposure / oxygen deprivation (-) | 0.032 |

For a complete list of programm arguments run:

```
nix-tumor3d -h
```

####2) Comparison with Data:
In order to compare the simulation results on the fly with given data, the following command can be used instead:

```
nix-compare2d DATA_FILES LIKELIHOOD_THRESHOLD PARAMETER_LIST
```

* The `DATA_FILES` are passed as

  | Argument | Description |
  | --- | --- |
  | `-g FILENAME` | growth curve\*\* |
  | `-k FILENAME` | day 17: KI67 positive / proliferating cell fraction* |
  | `-t FILENAME` | day 17: TUNEL positive / necrotic cell fraction* |
  | `-e FILENAME` | day 17: COLIV intensity / extra-cellular matrix (ECM) density* |
  | `-K FILENAME` | day 24: KI67 positive / proliferating cell fraction* |
  | `-T FILENAME` | day 24: TUNEL positive / necrotic cell fraction* |
  | `-E FILENAME` | day 24: COLIV intensity / extra-cellular matrix (ECM) density* |
  \* as function of the distance to the outer tumor border (\mu m)
  \*\* as function of time (days)
 
* The `LIKELIHOOD_THRESHOLD` indicates the value which will stop a running simulation if exeeded and will be returned back. It is passed as 
  
  ```-l FLOAT```
  
* `PARAMETER_LIST` is an optional list of 0 to 18 values corresponding to the model parameters in [Tab. 1](#table-1-model-parameters) 

  ```FLOAT ... FLOAT```

After finishing the simulation for the given model parameters the programm will print the likelihood to `stdout`. 
 
## Example Data
The directory `\data` contains 4 example data set with different error models:

| Files | 1st column (x) | 2nd column (y) | 3rd column (\sigma) |
| --- | --- | --- | --- |
| `SK-MES1_*.dat` | time (h) / distance (\mu m) | mean | **std** |
| `SK-MES1_*.dat.mean` | time (h) / distance (\mu m) | mean | **0.1 * mean** |
| `SK-MES1_*.dat.std` | time (h) / distance (\mu m) | mean | **std of mean (over all x)** |
| `SK-MES1_*.dat.minmax` | time (h) / distance (\mu m) | mean | **max mean - min mean (over all x)** |
