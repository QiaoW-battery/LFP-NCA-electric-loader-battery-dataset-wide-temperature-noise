# LFP and NCA Battery Dataset for Electric Loader Operating Conditions

This repository contains eight MATLAB data files for LFP and NCA batteries under electric loader operating conditions.

## Dataset files

| File | Chemistry | Approximate size |
| --- | --- | ---: |
| `cell_1.mat` | LFP | 797 MB |
| `cell_2.mat` | LFP | 733 MB |
| `cell_3.mat` | LFP | 707 MB |
| `cell_4.mat` | LFP | 693 MB |
| `cell_5.mat` | NCA | 845 MB |
| `cell_6.mat` | NCA | 845 MB |
| `cell_7.mat` | NCA | 845 MB |
| `cell_8.mat` | NCA | 897 MB |

The files total approximately 6.36 GB (5.93 GiB). Each MAT-file contains a structure named after the cell, such as `cell_1`.

## Temperature and operating conditions

Each cell structure contains the temperature-labelled fields `temp5`, `temp10`, `temp20`, `temp30`, `temp40`, `temp50`, and `temp55`. Each field contains `ocv` and `drivecycle_constant_temp` structures.

The constant-temperature drive cycles include `DST`, `BJDST`, `FUDS`, `US06`, `UDDS`, `Mix_1`, `Mix_2`, `I_loader`, and `V_loader`. `I_loader` and `V_loader` represent the I-type and V-type electric loader operating conditions.

Each cell also contains four dynamic-temperature structures:

- `dynamic_middle_temp_fullcharge`
- `dynamic_high_temp_fullcharge`
- `dynamic_middle_temp_notfullcharge`
- `dynamic_high_temp_notfullcharge`

## Data fields

| Field | Description |
| --- | --- |
| `volt` | Voltage |
| `current` | Current |
| `Q` | Capacity |
| `E` | Electric potential |
| `time` | Time |
| `soc` | State of charge |
| `temp` | Temperature |
| `ocv` | Open-circuit voltage |
| `R0` | Ohmic internal resistance |
| `R1` | Polarization resistance |
| `C1` | Polarization capacitance |
| `volt_om` | Ohmic voltage component |
| `volt_p` | Polarization voltage component |
| `volt_nn` | Equivalent circuit model (ECM) voltage error |

Field availability varies by cell and test. OCV structures include charge and discharge fields such as `ocv_dis`, `Q_dis`, `soc_dis`, `current_dis`, `E_dis` and their `_ch` counterparts.

## Download

The MAT files are stored using [Git Large File Storage (Git LFS)](https://git-lfs.com/). Install Git and Git LFS, then run:

```bash
git lfs install
git clone https://github.com/QiaoW-battery/LFP-NCA-electric-loader-battery-dataset-wide-temperature-noise.git
cd LFP-NCA-electric-loader-battery-dataset-wide-temperature-noise
git lfs pull
```

GitHub-generated source archives may not include the actual LFS files, depending on repository settings.

## Inspect the data in MATLAB

Set MATLAB's current folder to the downloaded repository. For example, inspect and load `cell_1.mat`:

```matlab
whos('-file', 'cell_1.mat')
data = load('cell_1.mat');
fieldnames(data)
```

To inspect the I-type loader record under `temp5`:

```matlab
record = data.cell_1.temp5.drivecycle_constant_temp.I_loader;
fieldnames(record)
```

## Citation and license

Please reference this repository when using the dataset. No dataset license has been specified; contact the repository owner about reuse or redistribution.
