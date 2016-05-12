# pABC-SMC

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

| Commandline Argument | Description | Default Value |
| --- | --- | --- |
| `-kdiv FLOAT` | division rate | 0.032 |

####2) Comparison with Data:
In order to compare the simulation results on the fly with given data, the following command can be used instead:

```
nix-compare2d DATA_FILES PARAMETER_LIST
```
The `DATA_FILES` are passed as
| `-g FILENAME` | growth curve |
| `-k FILENAME` | day 17: KI67 positive / proliferating cell fraction* |
| `-t FILENAME` | day 17: TUNEL positive / necrotic cell fraction* |
| `-e FILENAME` | day 17: COLIV intensity / extra-cellular matrix (ECM) density* |
| `-K FILENAME` | day 24: KI67 positive / proliferating cell fraction* |
| `-T FILENAME` | day 24: TUNEL positive / necrotic cell fraction* |
| `-E FILENAME` | day 24: COLIV intensity / extra-cellular matrix (ECM) density* |
* as function of the distance to the outer tumor border
 
## Example Data
The directory `data` contains 4 example data set.