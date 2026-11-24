# LFP and NCA Battery Dataset for Electric Loader Operating Conditions

This repository provides eight MATLAB data files for research on LFP and NCA batteries and electric loader operating conditions. The research considers I-type and V-type operating conditions, a wide temperature range, and noise effects. Details of test coverage and noise in each file remain to be verified.

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

The chemistry assignments above were provided by the dataset owner. The eight MATLAB 5 MAT-files total approximately 6.36 GB (5.93 GiB). Each file contains a top-level structure named after the file (for example, `cell_1`).

## Temperature and operating conditions

Each of the eight cell structures contains the temperature-labelled fields `temp5`, `temp10`, `temp20`, `temp30`, `temp40`, `temp50`, and `temp55`. These labels are listed exactly as stored; the temperature unit and the precise test conditions should be confirmed before interpreting the numbers.

Each temperature-labelled structure contains `ocv` and `drivecycle_constant_temp`. The drive-cycle structure contains `DST`, `BJDST`, `FUDS`, `US06`, `UDDS`, `Mix_1`, `Mix_2`, `I_loader`, and `V_loader`. `I_loader` and `V_loader` are the I-type and V-type electric loader profiles, respectively.

Each cell also includes these four structures:

- `dynamic_middle_temp_fullcharge`
- `dynamic_high_temp_fullcharge`
- `dynamic_middle_temp_notfullcharge`
- `dynamic_high_temp_notfullcharge`

The `fullcharge` structures include `I_loader` and `V_loader`; the `notfullcharge` structures include `I_loader_60`, `I_loader_70`, `I_loader_80`, `I_loader_90`, and the corresponding four `V_loader` fields. The exact temperature trajectories and meaning of the numeric suffixes require confirmation.

## Data fields

Common drive-cycle fields include `volt`, `current`, `Q`, `E`, `time`, and `soc`. Some dynamic records also contain `temp` and `ocv`. The `ocv` structures include `ocv_dis`, `Q_dis`, `soc_dis`, `current_dis`, `E_dis`, and corresponding `_ch` fields. Field names suggest voltage, current, time, state of charge, and charge/discharge quantities; their units, sign conventions, sampling rates, and the precise meanings of `Q` and `E` must be verified before use.

Some records also contain `ocv1`, `volt_om`, `volt_nn`, `volt_p`, `R0`, `R1`, `R2`, `C1`, and `C2`. According to the dataset owner, `R0` is ohmic internal resistance, `R1` is polarization resistance, `C1` is polarization capacitance, and `volt_nn` is the voltage loss predicted by the neural network. These fields include parameters or quantities associated with a first-order RC model. Their availability varies by cell and test; the precise definitions of the remaining fields and their units require confirmation. The presence or construction of noise in individual records also remains to be established.

For example, MATLAB can access the I-type loader record under the `temp5` label in `cell_1`:

```matlab
S = load('cell_1.mat');
record = S.cell_1.temp5.drivecycle_constant_temp.I_loader;
fieldnames(record)
```

## Download

The MAT files are stored using [Git Large File Storage (Git LFS)](https://git-lfs.com/). Install Git and Git LFS, then run:

```bash
git lfs install
git clone https://github.com/QiaoW-battery/LFP-NCA-electric-loader-battery-dataset-wide-temperature-noise.git
cd LFP-NCA-electric-loader-battery-dataset-wide-temperature-noise
git lfs pull
```

Allow enough disk space for the dataset. GitHub-generated source archives may not include the actual LFS files, depending on repository settings.

## Inspect the data in MATLAB

Set MATLAB's current folder to the downloaded repository. To inspect the variables and load a file, run:

```matlab
whos('-file', 'cell_1.mat')
data = load('cell_1.mat');
fieldnames(data)
```

To inspect a structure inside the file, use `fieldnames` on that variable. Each file is large and may require substantial memory to load. Verify field availability and units for the specific cell and test before analysis.

## Citation and contact

Author names, a recommended citation, and contact information will be added when confirmed. For now, please reference the repository URL when referring to the dataset.

## License

No dataset license has yet been specified. Contact the repository owner about permissions for reuse or redistribution.
