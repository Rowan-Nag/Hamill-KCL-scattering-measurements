# Hamill-KCL-scattering-measurements

Light scattering measurements using Exoplanet Cloud Ensemble Scattering System (ExCESS).
  - [Files](#files)
  - [Usage](#usage)
  - [License](#license)
## Files

**KCl_ScatteringData_Final**
- KCL Scattering data using particles of varying size. (using 532nm wavelength)
- Parameters
  - **Angle** - Scattering angle
  - **Phase function** - Measured Intensity at specified angles
    - *Normalized*: Normalized so that intensity is 1 at 30°
    - *SEM*: Standard error of the mean
  - **DOLP** - Degree of Linear Polarization
    - *SEM*: Standard error of the mean

**KCl_SizeData_Final**
- particle sizes for the three different size distributions as measured by the optical particle sizer (OPS)

**PSL_ScatteringData_Final**
- PSL (polystyrene latex) spheres scattering data, used for verifying accuracy of ExCESS Measurements
- Parameters
  - **Angle** - Scattering angle
  - **Phase function** - Measured Intensity at specified angles
    - *Normalized*: Normalized so that intensity is 1 at 30°
    - *SEM*: Standard error of the mean
  - **DOLP** - Degree of Linear Polarization
    - *SEM*: Standard error of the mean
## Usage

All data is in CSV format. <br>
Below is an example retrieving the *LargeKCL_532nm_Final.txt* data in Python, with the Pandas library ([Installation](https://pandas.pydata.org/docs/getting_started/install.html)). <br>
This example can be used with all the KCl & PSL Scattering data, by using the path to the desired file.

```python
import pandas as pd

LargeKCL_532nm = pd.read_csv(
    'KCl_ScatteringData_Final/LargeKCl_532nm_Final.txt', # Filepath. 
    header = 0,
    names = ['angle', 'phase_func_normalized', 'phase_func_SEM', 'DOLP', 'DOLP_SEM']
)

# Reference individual Columns:
LargeKCL_532nm['angle'] # can use any column name.
```


## License
[![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg