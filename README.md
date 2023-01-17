<!---

    Copyright (c) 2019 Robert Bosch GmbH and its subsidiaries.

-->

This repository contains the companion material for the following publication:
> Tnani, Mohamed-Ali; Feil, Michael; Diepold, Klaus. Smart Data Collection System for Brownfield CNC Milling Machines: A New Benchmark Dataset for Data-Driven Machine Monitoring. Procedia CIRP2022,107, 131–136.

# CNC Machining Data 

Please cite this paper if using the dataset and direct any questions regarding the dataset to [Tnani Mohamed-Ali](mailto:mohamed-ali.tnani@boschrexroth.de). The paper can be found at the [CIRP CMS](https://doi.org/10.1016/j.procir.2022.04.022).

## General information and Context
The dataset provided is a collection of real-world industrial vibration data collected from a brownfield CNC milling machine. The acceleration has been measured using a tri-axial accelerometer (Bosch CISS Sensor) mounted inside the machine. The X- Y- and Z-axes of the accelerometer have been recorded using a sampling rate equal to 2 kHz. Thereby normal as well as anomoulous data have been collected for 6 different timeframes, each lasting 6 months from October 2018 until August 2021 and labelled accordingly. It can be used to investigate the scalability of models and research process variations as the anomaly impact differs. In total there is data from three different CNC milling machines each executing 15 processes. For a detailed description of the data and experimental set-up, please refer to the paper. 

## Dataset:

The data are located in the `data` folder.

### Folder structure: 

The `data` directory containing the manually annotated machine processes is structured as follows:
```
data/
    machine number/             Corresponding machine number. We have data from 3 machines (M01, M02, M03)
        process number/         Coresponding process number. We have 15 different processes (OP00, .., OP14)
            label/              Coresponding process health. "good": Normal vibrational data, "bad": Anomalous vibrational data
                filename:       .h5 file containing the vibration data. The files are annotated as follows: Machine no. + timeframe + Process no + example no. e.g. M02_Aug_2019_OP03_000.h5
    
```

### Data structure: 

The .h5 file contains the label of the process and is structured as follows: 
```
   vibration data         the dataset contains a ndarray of dimension (acc_values, n_channels). (n_channels: acceleration axis: 0: X-axis, 1:Y-axis, 2:Z-axis)
    
```

## Code

### Installation Requirements

The code provided for loading the data has been written in Python 3.8. You need the following conda packages: `h5py`, `numpy` and `matplotlib`. The script `utils/data_loader_utils.py` proposes functions to load and vizualize the data. The notebook `Data_explorer.ipynb` shows how those functions can be used.


## License
The code in this repository is open-sourced under the BSD-3-Clause license. See the [License](utils/License) file for details.

The dataset created for the research located in the directory [data](data) are licensed under a [Creative Commons Attribution 4.0 International
License](http://creativecommons.org/licenses/by/4.0/) (CC-BY-4.0).
