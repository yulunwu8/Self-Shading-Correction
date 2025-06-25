# Self-Shading Correction

## Description

Applies self-shading correction to water-leaving reflectance measurements collected through the skylight-blocked approach, following Yu et al. (2021).

- Valid for wavelengths between **300** and **1000 nm**. (Extending beyond this range requires additional water backscattering data)
- Input reflectance must include bands at or near **440 nm**, **550 nm**, and **750 nm**. (The closest available wavelengths are used)


Home page: <a href="https://github.com/yulunwu8/selfshadingcorrection" target="_blank">https://github.com/yulunwu8/selfshadingcorrection</a>


## Installation 

```bash
pip3 install selfshadingcorrection
```



## Quick Start

```python
import selfshadingcorrection as ssc

file_in = 'Rw_shaded.csv'        # Path to input CSV with shaded water-leaving reflectance.
file_out = 'Rw_corrected.csv'    # Path to output CSV with self-shading-corrected reflectance.
start_column = 10                # Index of the first reflectance column (0-based).
sza_column = 'sza'               # Name of the column containing solar zenith angle (in degrees).
radius = 0.05                    # Radius of the instrument cone (in meters).

ssc.run(file_in, file_out, start_column, sza_column, radius)
```



**Input Data Format**

- **Examples**: See example input and output data at in the selfshadingcorrection/tests folder.
- **Metadata columns** (before start\_column): All metadata columns will be copied to the output as is. Must include a column for the solar zenith angle in degrees. 
- **Reflectance columns** (starting at start\_column):
Column names should follow the format Rxxx, where xxx is the wavelength in nm.
- **Reflectance values**:
Bi-hemispherical water-leaving reflectance (dimensionless).



## Reference 

Yu, X., Lee, Z., Shang, Z., Lin, H., Lin, G., 2021. A simple and robust shade correction scheme for remote sensing reflectance obtained by the skylight-blocked approach. Opt. Express 29, 470. <a href="https://doi.org/10.1364/OE.412887" target="_blank">https://doi.org/10.1364/OE.412887</a>


## Others

For questions and suggestions (which I'm always open to!), please open an issue or email Yulun at [yulunwu8@gmail.com](mailto:yulunwu8@gmail.com)

