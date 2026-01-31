# Xinanjiang (XAJ) Single-Basin Reproducibility Package

This repository provides a runnable single-basin example of the Xinanjiang (XAJ) hydrological model and its parameter calibration using a modified implementation of the SPOTPY optimization framework. The package is designed to support reproducibility of the modeling workflow used in the associated Earth’s Future manuscript, rather than to reproduce all basin-scale experiments reported in the paper.

---

## Contents of the Package

The main files and folders included in this package are described below.

### `run_example.py`
The main entry script of the reproducibility package.  
Running this script executes a complete example workflow for a representative basin, including:
- loading example forcing and streamflow data,
- running the XAJ hydrological model,
- calibrating model parameters using the SCE-UA algorithm,
- and generating example outputs.

This script is intended to be run directly by users to verify the modeling framework.

---

### `xaj.py`
The core implementation of the Xinanjiang (XAJ) hydrological model used in this study.  
This file defines the model structure and water balance calculations and is called internally by the calibration and linkage routines.

---

### `spot_xaj.py`
A linkage script that connects the XAJ model (`xaj.py`) with the SCE-UA optimization algorithm.  
This script defines the objective function and serves as the interface between the hydrological model and the parameter optimization procedure.

---

### `spotpy/`
A modified version of the SPOTPY (Statistical Parameter Optimization Tool for Python) package.  
This folder contains the implementation of the SCE-UA algorithm used for parameter calibration in this study.  
The version provided here includes minor modifications made by the authors to support the calibration workflow and output handling.

---

### `Parm/`
A directory used to store parameter settings and intermediate files generated during the calibration process.  
This folder contains configuration files and temporary outputs required for running the example calibration and is accessed automatically by the scripts.

---

### `data_input.xlsx`
An example input dataset for the representative basin.  
This file includes:
- precipitation and potential evapotranspiration forcing data,
- basin-level attributes (e.g., catchment area),
- and example streamflow data used for model calibration and evaluation.

The dataset is provided solely for demonstration and reproducibility purposes.

---

### `streamflow.png`
An example figure showing simulated and reference streamflow produced by the example run.  
This figure illustrates the expected output of the model workflow and serves as a visual check of successful execution.

---

## How to Run the Example

1. Download the full package as a ZIP file and extract it.
2. Make sure you are in the extracted directory.
3. Run the example script:

```bash
python run_example.py
