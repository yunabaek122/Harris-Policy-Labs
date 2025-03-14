# Harris Policy Labs - IDinsight Analysis Code Files

## Description

This repository (folder) consists raw datafiles and code scripts used to conduct analyses on the Arab Barometer and Afrobarometer datasets. The code includes non-exhaustive code chunks that illustrate how the data analysis was conducted. While extensive exploratory analyses were performed, the code provided in the markdown files prioritizes the final analyses that led to our key findings. 

## Repository Overview
This repository contains analysis code used to examine public perceptions of governance, democracy, and civic engagement using survey data from Afrobarometer (Rounds 7 & 9) and Arab Barometer (Wave 9). The provided scripts include one Python notebook and two R Markdown files, which handle data importation, preprocessing (e.g., cleaning, recoding variables), descriptive statistics (frequencies, means, visualizations), exploratory correlation analyses, balance tests, creation of summary indices, and regression modeling (logit and OLS). The analyses specifically investigate the relationships between people's experiences and perceptions of respect and dignity and key predictive variables (e.g., institutional trust, political participation, and etc.) along with demographic factors (e.g., gender, education, etc.). Each step in the code is clearly documented to facilitate transparency, reproducibility, and ease of adaptation for future analyses.

* Arab Barometer W8 Statistical Analysis: Arab Wave 8 Statistical Analysis Code.Rmd
* Afrobarometer R7 & R9 Descriptive Statistics: Afro_R7_&_9_Descriptive_Statistics_Code.ipynb
* Afrobarometer R9 Statistical Analysis: Afro R9 Statistical Analysis Code.Rmd

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
#### File name
Arab Wave 8 Statistical Analysis Code.Rmd
#### Purpose: 
* Conducts exploratory analyses and descriptive statistics for the Afrobarometer Round 9 dataset
* Explores key survey variables, examine their distributions, clean and recode the dataset, visualize relationships, and perform initial inferential statistical modeling, including logistic regressions with interaction terms

#### Code Structure:
#### 1. Data Wrangling and Cleaning
* Recodes special response values (e.g., 98, 99, 97) to missing (NA) across all relevant variables, ensuring accurate subsequent analyses.
#### 2. Variables Processing
* Transforms key survey questions (e.g., Q551A as the dependent variables, demographic variables, socio-Economic status variables) into binary dummy variables to facilitate logistic regression modeling.

#### 3. Data Visualization
* Bar plots of binary financial stability indicators, displaying distributions clearly including missing data.
* Heatmap visualizations of Spearman correlation matrices among key socioeconomic variables.

#### 4. Logit Model
  - Two custom functions, `run_glm_models` and `run_int_models`, are used to explore and perform the following analyses:
    - `run_glm_models`: Runs logit models with and without demographic variables as control variables.
    - `run_int_models`: Runs a logit model with demographic variables as interaction terms.
#### 5. Predicted Probability Plots
* Visualizes logistic regression results using predicted probability plots, facilitating intuitive understanding of relationships between key variables and demographic subgroups.

## Afrobarometer
#### File name
Afro R9 Statistical Analysis Code.Rmd
#### Purpose:
* Conducts correlation analyses, constructs indices for key conceptual variables (such as respect, socioeconomic status, absence of corruption, and civil rights)
* Performs regression modeling to test hypotheses, evaluates diagnostics and reliability, and conducts country-specific analyses.
#### Setup:
* Installs and loads essential R libraries including haven, dplyr, Hmisc, ggplot2, reshape2, and etc. for data handling, statistical analysis, and visualization. Review the top of each R Markdown file for additional library() calls you might need.
* Data Import: Reads Afrobarometer Round 9 data from an SPSS (.sav) file
```
library(heavn)
path.to.data <- "your_path"
afro_R9 <- read_sav(path.to.data)
```
#### Code Structure: 
#### 1. Data Cleaning and Preparation
* Converts special numeric codes (-1, 8, 9, 94, 98, 99) and specific survey responses (e.g., "No contact", "Refused", "Don't know") to missing values (NA).

#### 2. Correlation Analysis
* Performs Spearman correlation analyses among core respect questions (Q40D, Q41D, Q42D).
* Visualizes correlations using heatmaps and provides significance levels and effect size classifications.

#### 3. Index Construction
- Constructs composite indices for 5 key thematic areas:
  1. Governance: Equality under law, Absence of corruption, Free elections, Civil rights, Trust
  2. Security: Physical safety, Presence of security forces
  3. Economic wellbeing: Basic necessities, Access to services
  4. Equity & inclusion: Gender discrimination, Other discrimination
  5. Civic engagement: Social engagement, Political engagement
* Recodes survey responses to align directions consistently (higher values represent positive outcomes).

#### 4. Regression Analysis (OLS Models)
* Constructs the primary dependent variable (Respect Index).
* Includes demographic factors (gender, education, urban/rural status) and socioeconomic status (SES) as controls.
* Runs full regression models incorporating all main indices.
* Conducts interaction analyses and split-sample regressions based on SES.

#### 5. Diagnostics and Reliability
* Evaluates model assumptions through:
* Residual diagnostics (QQ-plots, residual vs. fitted plots).
* Formal statistical tests for normality (Anderson-Darling test) and heteroscedasticity (Breusch-Pagan test).
* Checks internal consistency and factor structure of the respect items using Cronbach’s alpha and exploratory factor analysis (EFA).

#### 6. Country-Specific Analysis
* Performs detailed country-level cross-tabulations and chi-square tests on respect-related survey items (Q40D, Q41D, Q42D).
* Visualizes country-specific differences in perceived respect using bar graphs.
* Conducts country-level regression analyses to explore variations in determinants of respect perceptions.


### Github Repo
https://github.com/yunabaek122/Harris-Policy-Labs
