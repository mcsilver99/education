# Education Project 

> This project aims to analyze the correlation between socioeconomic factors and student-teacher ratios in relation to average ACT scores. The goal is to develop a model that accurately predicts school performance based on these variables.

---

## Project Overview

This project addresses inequality of educational opportunity in U.S. high schools. Here we will focus on average student performance on the ACT or SAT exams that students take as part of the college application process.

A range of school performance is expected on these exams, but is school performance associated with socioeconomic factors?

The project will additionally analyze if there is an association between ACT score and student-teacher ratio, and if so, if that is a good predictor for ACT performance. 

- **Objective:** To analyze what kind of socioeconmic factors, if any, affect average ACT score. 
- **Domain:** Education
- **Key Techniques:** Simple linear regression, multiple linear regression

---

## Project Structure

```
├── data/                           # Raw and processed data
│   ├── edgap.xlsx                        
│   ├── ccd_sch_029_1617_w_1a_11212017.csv 
│   ├── ELSI_csv_export_2017.csv
│   ├── education_clean.csv         # Cleaned datasets ready for analysis                
├── code/                           # Jupyter notebooks
│   ├── Education.ipynb             # Data loading, filtering, and outlier removal, exploratory
├── reports/                        # Generated reports and visualizations
│   └── education_results.pdf       # Complete analysis report
├── requirements.txt                # Python dependencies
└── README.md                       # Project documentation
```

---

## Data

- **Source:** https://www.edgap.org/#5/37.875/-96.987, https://nces.ed.gov/ccd/pubschuniv.asp, https://nces.ed.gov/ccd/elsi/default.aspx?agree=0
- **Description:** This project utilizes 3 data sets EdGap_data.xlsx, ccd_sch_029_1617_w_1a_11212017.csv, and ELSI_csv_export_2017.csv. The primary data set is the EdGap data set from EdGap.org. This data set from 2016 includes information about average ACT or SAT scores for schools and several socioeconomic characteristics of the school district. The secondary data set is basic information about each school from the National Center for Education Statistics (NCES). The third data set comes from the NCES Elementary and Secondary Information System table generator where the student to teacher ratio data was selected for the 2016/2017 school year. Data is disaggregated by school, LEA, Educational Service District, and the state level. 
- **License:** N/A

---

## Analysis

Data were filtered to include only high schools, with student-teacher ratios restricted to the middle 98% (removing extreme outliers). Schools with missing ACT scores were excluded, while missing values for other predictors were imputed using IterativeImputer to prevent loss of data.

Analysis proceeded in three stages. First, simple linear regression examined the relationship between student-teacher ratio and ACT scores. Second, multiple linear regression incorporated all socioeconomic predictors. Third, model comparison evaluated three specifications: the full model with all variables, a reduced model retaining only statistically significant predictors, and a modified full model excluding student-teacher ratio.

---

## Results

Student-teacher ratio alone explains less than 1% of the variance in ACT scores (R² = 0.002), despite being statistically significant (p = 0.001). In contrast, socioeconomic variables—including unemployment rate, percent of adults with higher education, and percentage of students eligible for free or reduced lunch—demonstrated substantially stronger predictive power. When both sets of variables were included in a multiple regression model, student-teacher ratio did not noticeably improve performance, suggesting it has limited practical value for predicting ACT scores when socioeconomic factors are considered.

---

## Authors

- Maya Silver - [@mcsilver99](https://github.com/mcsilver99)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- statsmodels, sklearn, seaborn
- Whitehurst, G. J., & Chingos, M. M. (2011). Class size: What research says and what it means for state policy. Brookings Institution. https://www.brookings.edu/articles/class-size-what-research-says-and-what-it-means-for-state-policy/
