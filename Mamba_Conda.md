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


Create a new environment
```
conda create -n py311 python=3.11
conda activate py311
conda install numpy scipy pandas matplotlib spyder plotly
conda deactivate
```


Update all libraries inside an environment
```
conda update -n py311 --all
```
