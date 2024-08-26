![alt text](https://github.com/gammapy/gammapy-extra/blob/master/logo/gammapy_banner.png?raw=true)


# Hands-on workshop on VHE gamma-ray data analysis using Gammapy

This folder contains the analysis notebooks shown in the Gammapy hands on sessions for the ORP School on Multi-messenger Astrophysics. 
The related page can be found at https://www2.mpia-hd.mpg.de/~korhonen/ORP_training/Multi/

## Installation and set-up

Note: for this tutorial session we will actually utilise Google Collab for ease. However, it is wise to have gammapy installed in case we have any issues.

These instructions assume that you have previously installed a version of [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) on your machine.

### Gammapy installation


We recommend that you install the latest version of gammapy (v1.2) as follows: 

```
curl -O https://gammapy.org/download/install/gammapy-1.2-environment.yml
conda env create -f gammapy-1.2-environment.yml
conda activate gammapy-1.2
```

OR with `pip`
```
python -m pip install gammapy[all]
```

### Download tutorials & associated data

To download the tutorials and associated datasets (necessary for the tutorials in this workshop)

```
gammapy download notebooks
gammapy download datasets
```

If using conda environment, set GAMMAPY_DATA with conda
```
conda env config vars set GAMMAPY_DATA=$PWD/gammapy-datasets/1.2
conda activate gammapy-1.2
```

else set with shell:
```
export GAMMAPY_DATA=$PWD/gammapy-datasets/1.2
```

### Check your installation

To check that the gammapy environment is working, open a new terminal and type

```
conda activate gammapy-1.2
gammapy info
```
To further check that you have correctly set up the data folder type

```
ipython
```

Then in the ipython window, type
```
from gammapy.data import DataStore
ds = DataStore.from_dir("$GAMMAPY_DATA/hess-dl3-dr1")
obs = ds.get_observations()
print(len(obs))
```

If the cells run without any error and prints `105`, **Congratulations! You have correctly set-up gammapy**


### If you have any issues with installation please contact Kirsty via email feijen@apc.in2p3.fr or come see me during the week before the session (4:30PM Wednesday 4th September)


## Jupyter notebook
For this hands-on session we will utilise jupyter notebook, so please ensure you have the installed in your conda environment. 
To begin the session you can simply type the following in your terminal:
```
conda activate gammapy-1.2
jupyter notebook
```

## GitHub
I will distribute the code and all materials discussed in the ORP on this GitHub page. If you are new to GitHub you can follow the below instructions to obtain this repository on your own laptop. 

The first step is to clone this repository:
```
git clone https://github.com/Astro-Kirsty/gammapy-ORP.git
```
Now you have a local copy of the repository. To get any changes from the repo you can do:
```
git pull
```



## Timetable Wednesday 4th September

- 9:30AM - 11AM 	Introduction to high energy gamma-ray observations (Paula Chadwick)
- 11AM - 11:30AM 	Break
- **11:30AM - 1PM 	Introduction to the tools used in gamma-ray astrophysics (Kirsty Feijen)**
- 1PM - 2PM 	Lunch
- 2PM - 4PM 	Hands-on work on FERMI data (Cameron Rulten, Sheridan Lloyd)
- 4PM - 4:30PM 	Break
- **4:30PM - 6:30PM 	Hands-on work on gammapy (Kirsty Feijen)**
