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

|Commandline Argument| Description | Default Value|

####1) Tumor Simulation:

## Example Data
