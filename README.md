# LFP and NCA Battery Dataset for Electric Loader Operating Conditions

This repository provides eight MATLAB data files for research on LFP and NCA batteries and electric loader operating conditions. The research considers I-type and V-type operating conditions, a wide temperature range, and noise effects. Details of test coverage and noise in each file remain to be verified.

## Dataset files

| File | Approximate size |
| --- | ---: |
| `cell_1.mat` | 797 MB |
| `cell_2.mat` | 733 MB |
| `cell_3.mat` | 707 MB |
| `cell_4.mat` | 693 MB |
| `cell_5.mat` | 845 MB |
| `cell_6.mat` | 845 MB |
| `cell_7.mat` | 845 MB |
| `cell_8.mat` | 897 MB |

The eight files total approximately 6.36 GB (5.93 GiB). Each is a MATLAB 5 MAT-file. The battery chemistry, capacity, aging condition, experimental conditions, temperature values, measurement units, and sampling rate for each file will be documented after verification.

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

To inspect a structure inside the file, use `fieldnames` on that variable. Each file is large and may require substantial memory to load. A detailed data dictionary will be added after the fields and units have been verified.

## Citation and contact

Author names, a recommended citation, and contact information will be added when confirmed. For now, please reference the repository URL when referring to the dataset.

## License

No dataset license has yet been specified. Contact the repository owner about permissions for reuse or redistribution.
