# COVID-19 Comorbidities Analysis

This repository contains a data analysis project focused on understanding the relationship between pre-existing comorbidities and COVID-19 outcomes, using synthetic healthcare data from [Synthea](https://synthetichealth.github.io/synthea/). The analysis aims to identify common comorbidities in COVID-19 patients and determine their influence on outcomes such as death or hospitalization.

## Project Overview

In this project, we analyze:
- The demographic structure of COVID-19 patients.
- Common comorbidities and their distribution across different age groups.
- Differences in the prevalence of comorbidities between survivors and non-survivors.
- Statistically significant relationships between comorbidities and death using the Chi-Square test.

This is a work in progress, and the analysis will continue to evolve as more insights are discovered.

## Data Acquisition

### Source of Data
The data was acquired from a course-provided database built on the OMOP Common Data Model, populated with synthetic healthcare data from Synthea.

### Tables Used:
- `covid_occurrences.csv`: Isolates the first COVID-19 diagnosis for each patient.
- `covid_person.csv`: Contains demographic data (age, gender, race, etc.) for patients diagnosed with COVID-19.
- `covid_comorbidities.csv`: Lists ongoing conditions present before or during COVID-19 diagnosis.
- `covid_deaths.csv`: Records all deaths among patients diagnosed with COVID-19.
- `covid_drug_exposures.csv`: Captures drug treatments administered during COVID diagnosis.
- `covid_procedures.csv`: Captures medical procedures performed during the COVID-19 diagnosis period.

These tables were generated from SQL queries and then exported as `.csv` files for further analysis.

## Structure

### Data Acquisition
1. **SQL Queries:** SQL code to acquire and process the necessary data from the course database is stored in `data_acquisition_overview.ipynb`.
   - Isolating COVID-19 occurrences.
   - Extracting demographic data (`covid_person`).
   - Extracting comorbidities, death records, and related conditions (`covid_comorbidities`, `covid_deaths`).
   
2. **CSV Files:**
   - `covid_occurrences.csv`
   - `covid_person.csv`
   - `covid_comorbidities.csv`
   - `covid_deaths.csv`
   - `covid_drug_exposures.csv`
   - `covid_procedures.csv`

3. **Notebook:** The code for processing these datasets is available in the notebook `covid_analysis.ipynb`.

## Analysis Outline

### Loading and Merging Datasets
- Merge `covid_occurrences` with `covid_person` for unified demographic and occurrence data.
- Load and merge comorbidities and death data for further analysis.

### Exploring Demographics
- Visualize and explore demographic data: age, gender, ethnicity, and race.
- Group patients by age ranges (e.g., 30-39, 40-49) for better comparison.

### Comorbidity Analysis
- Explore the most common comorbidities present in the COVID-19 positive population.
- Filter and clean redundant or flawed conditions (e.g., diabetes or miscarriage).

### Mortality Analysis
- Explore the death data, removing duplicates and non-COVID related deaths.
- Visualize deaths across different age groups.

### Statistical Testing
- Use Chi-Square tests to compare the prevalence of comorbidities in the general COVID-19 positive population and those who passed away.
- Identify statistically significant differences between these two groups.

### Visualizations
- Bar plots and comparisons showing comorbidity prevalence in the general population vs. the deceased population.
- Visualizations of age distributions and comorbidity distributions across age groups.

## Future Work
- Incorporate medication and procedure data into the analysis to explore their impact on COVID-19 outcomes.
- Investigate findings such as increased prevalence of appendicitis and substance abuse in the deceased population.
- Consider further exploration into mental health conditions and their role in COVID-19 outcomes.
- Explore potential confounding factors like socioeconomic status and other health disparities.


