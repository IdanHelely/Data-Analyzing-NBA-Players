# What Determines NBA Player Salaries?

### A Comparative Analysis of Offensive and Defensive Performance Metrics

**Final Project – Introduction to Data Science (R)**

---

## Team Members

* Idan Helely
* Michal __________
* Ganit Golin
* Noam Molay

---

# Project Description

This project investigates which on-court performance metrics have the strongest influence on NBA player salaries and whether offensive performance contributes more to salary determination than defensive performance.

Using player statistics from the 2015–2016 NBA season, we build separate multiple linear regression models for offensive and defensive player groups. Variable selection is performed using **AIC Stepwise Regression**, while controlling for player experience, height, and minutes played.

The project includes statistical modeling, model comparison, and visualizations that illustrate how different performance metrics contribute to NBA salaries.

---

# Repository Structure

```
Project/
│
├── README.md
├── final R.R                 # R script used for the analysis
├── Data.xlsx                 # NBA dataset
├── FinalReport.pdf           # Final project report
└── Presentation.pdf          # Project presentation (if included)
```

---

# Dataset

The dataset contains technical and statistical information for **95 NBA players** during the **2015–2016 NBA season**.

The main variables used in the analysis include:

### Performance Metrics

* Field Goals
* Free Throws
* Assists
* Total Rebounds
* Steals
* Blocks
* Turnovers
* Personal Fouls

### Player Characteristics

* Salary
* Position
* Height
* Experience
* Minutes Played
* Player Name

Players were divided into two groups according to their playing positions:

* **Offensive players:** Point Guards (PG), Shooting Guards (SG), Small Forwards (SF)
* **Defensive players:** Power Forwards (PF), Centers (C), Small Forwards (SF)

Small Forwards were included in both groups because they commonly contribute to both offensive and defensive play.

---

# Research Question

**Which performance metrics have the strongest influence on NBA player salaries, and does their impact differ between offensive and defensive players?**

---

# Methods

The analysis consists of the following steps:

1. Load and clean the dataset.
2. Rename variables for easier processing.
3. Convert salary values to millions of dollars.
4. Split players into offensive and defensive position groups.
5. Build baseline multiple linear regression models using control variables:

   * Experience
   * Height
   * Minutes Played
6. Build full regression models including all performance metrics.
7. Apply **AIC Stepwise Regression** to select the final models.
8. Compare the resulting offensive and defensive models.
9. Generate the figures used in the final report.

---

# Required R Packages

The project requires the following R packages:

```r
library(tidyverse)
library(readxl)
library(MASS)
library(broom)
library(scales)
library(rsq)
library(lm.beta)
```

If necessary, install them using:

```r
install.packages(c(
  "tidyverse",
  "readxl",
  "MASS",
  "broom",
  "scales",
  "rsq",
  "lm.beta"
))
```

---

# Reproducing the Analysis

To reproduce the analysis:

1. Download or clone this repository.

2. Place **Data.xlsx** in the project directory (the same folder as the R script).

3. Open **final R.R** in RStudio.

4. Make sure the dataset is loaded using a relative path:

```r
nba <- read_excel("Data.xlsx")
```

If your script currently contains an absolute path, replace it with the line above.

5. Run the script from beginning to end.

---

# Output

Running the script produces the figures included in the report:

* Offensive model coefficient estimates with 95% confidence intervals
* Defensive model coefficient estimates with 95% confidence intervals
* Salary distribution across performance quartiles
* Standardized coefficient comparison between offensive and defensive models

---

# Notes

* The analysis was developed using **R** and **RStudio**.
* Multiple linear regression was used together with **AIC Stepwise Regression** for variable selection.
* Control variables (Experience, Height, and Minutes Played) were retained throughout the model-building process.
* The dataset is provided separately from the code, in accordance with the course submission requirements.

---

# Citation

This project was completed as the final project for the **Introduction to Data Science** course (382.1.2601), Ben-Gurion University.
