# Mamba / Conda

https://github.com/conda-forge/miniforge#mambaforge


Manually download .zip file and install 

OR

```
wget "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh"
bash Mambaforge-$(uname)-$(uname -m).sh
```


Update Mamba
```
mamba update -n base mamba
```


Update all libraries inside an environment
```
conda update -n py310 --all
```

Create a new environment
```
conda create -n py311 python=3.11
```
Activate/Deactivate
```
conda activate py311
conda deactivate
```
