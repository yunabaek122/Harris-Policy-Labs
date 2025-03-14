# Harris Policy Labs - IDinsight Analysis Code Files

## Description

This repository (folder) consists raw datafiles and two R markdown files with code used to conduct analyses on the Arab Barometer and Afrobarometer datasets. The code includes non-exhaustive code chunks that illustrate how the data analysis was conducted. While extensive exploratory analyses were performed, the code provided in the markdown files prioritizes the final analyses that led to our key findings. 

### Data Files

* Arab Barometer W8: ArabBarometer_WaveVIII_English_v1.csv
* Afrobarometer R9: R9.Merge_39ctry.20Nov23.final.release_Updated.25Oct24 2 2.sav

### Executing codes

* Change path.to.data to replicate codes

```
path.to.data <- "your_path"
arab_df <- read_csv(path.to.data)
```

## Code Scripts

Analysis codes include the following contents. 

* Data wrangling
* Balance test
* Exploratory correlation analysis
* Summary indices
* Regression Analysis


## Arab Barometer
* Dependent variable: `Q551A` (coded as 6 binary variables)
* **Logit Model:** 
  - Two custom functions, `run_glm_models` and `run_int_models`, are used to explore and perform the following analyses:
    - `run_glm_models`: Runs logit models with and without demographic variables as control variables.
    - `run_int_models`: Runs a logit model with demographic variables as interaction terms.

## Afrobarometer
* Dependent variables: `Q40D`, 'Q41D', 'Q42D'
* **OLS Model** 


### Github Repo
https://github.com/yunabaek122/Harris-Policy-Labs
