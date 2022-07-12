# Undrift
Corrects local, non-linear drift in tissue by estimating dense optical flow and
using it for warping images back to first frame.

It comes as command line tool for Python >= 3.6

Please refer to Hansen et al 2022 for citation: https://doi.org/10.1093/oons/kvac009

### What does it do?
#### Original movie with non-linear, local drift in the tissue
![Original](example/res/a_orig.gif) 

#### Drift estimation via smooth, dense optical-flow
![Drift estimation](example/res/b_drift.gif) 

#### Undrifting result
![Undrift](example/res/c_undrift.gif)

### Installation
1. Clone repository to `<path>`
2. With (Ananconda) command line `cd <path>/undrift`
3. Pip install undrift with:

    ```pip install -r requirements.txt -e .```

Required python packages are installed automatically

### Usage

Basic command:

```undrift <movie_tif_file> [<more_tif_files>...]```

Command line help:

```undrift --help```

### How to apply recursively to many images in folder sturcture on Windows?
to use undrift with spatial smoothing of 50 px for all tif files in a folder recursively on Windows, use

```for /r %i in (*.tif) do undrift --smooth_xy 50 "%i"```

in the (Anaconda) command prompt
