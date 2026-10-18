# HR Employee Attrition Analysis

Portfolio project | Data Analyst Intern | Python · Google Colab · Pandas · NumPy · Matplotlib · Seaborn · Power BI

## Project overview

This project analyzes employee-level HR data to understand which characteristics are associated with employees leaving a company. It complements a separate retail sales and profitability analysis project.

The unit of analysis is one employee. This is a descriptive analytics project, not a machine learning or causal inference study. The analysis notebook is written in Vietnamese.

## Business objectives and questions

1. Measure the overall attrition rate.
2. Compare attrition rates across departments.
3. Examine attrition by overtime, tenure, age group, monthly income, job satisfaction and commute distance.
4. Compare the profile of employees who left with those who stayed.
5. Develop testable recommendations to improve employee retention.

## Dataset

`HR_Attrition_Cleaned.csv` is a **synthetic dataset created for this portfolio project**. It does not contain real employee data, and the findings below illustrate an analytical workflow rather than real company performance.

| Property | Value |
|---|---|
| Rows | 400 employees |
| Missing values | 0 |
| Duplicate rows / duplicate Employee_ID | 0 / 0 |

| Column | Description |
|---|---|
| Employee_ID | Unique employee identifier |
| Age | Age in years |
| Gender | Male, Female |
| Department | Sales, R&D, HR, IT, Finance |
| Years_At_Company | Tenure in whole years |
| Monthly_Income | Monthly income |
| Overtime | Whether the employee works overtime (Yes, No) |
| Job_Satisfaction | Satisfaction score from 1 (low) to 4 (high) |
| Distance_From_Home_km | Commute distance in kilometers |
| Attrition | Whether the employee left (Yes, No) |
| Age_Group | <30, 30-39, 40-49, 50+ |
| Tenure_Group | 0-2 yrs, 3-5 yrs, 6-10 yrs, 10+ yrs |
| Attrition_Flag | 1 if Attrition is Yes, otherwise 0 |

## Tools and technologies

Python, Pandas, NumPy, Matplotlib, Seaborn, Google Colab, Power BI Desktop.

## Analysis workflow

1. Load `HR_Attrition_Cleaned.csv` and inspect dimensions, data types, missing values, duplicates and descriptive statistics.
2. Validate required columns, unique Employee_ID, value ranges, and consistency between Attrition and Attrition_Flag.
3. Create income band and commute distance band features.
4. Calculate attrition KPIs.
5. Analyze attrition rates by department, overtime, tenure, age, income, satisfaction, distance and gender.
6. Compare employees who left with those who stayed, and generate data-derived insights.
7. Build an interactive Power BI dashboard from the same dataset.

## KPIs and methodology

| KPI | Definition |
|---|---|
| Total Employees | Count of employee rows |
| Employees Left | Count of Attrition == Yes (sum of Attrition_Flag) |
| Employees Stayed | Total Employees − Employees Left |
| Attrition Rate | Employees Left / Total Employees × 100% |

Group-level attrition rate is the number of employees who left in the group divided by the number of employees in the group. Comparisons of the highest and lowest department rates exclude groups with fewer than 30 employees. This is a descriptive sample-size filter, not a statistical significance test.

## Key findings

| KPI | Value |
|---|---|
| Total Employees | 400 |
| Employees Left | 100 |
| Employees Stayed | 300 |
| Attrition Rate | 25.0% |
| Average Monthly Income | 6,507.90 |
| Average Tenure | 5.0 years |

**Overtime**

| Overtime | Employees | Left | Attrition rate |
|---|---|---|---|
| No | 275 | 54 | 19.6% |
| Yes | 125 | 46 | 36.8% |

Employees working overtime leave at 1.9 times the rate of those who do not.

**Department**

| Department | Employees | Left | Attrition rate |
|---|---|---|---|
| Sales | 121 | 40 | 33.1% |
| R&D | 119 | 32 | 26.9% |
| HR | 34 | 9 | 26.5% |
| IT | 89 | 14 | 15.7% |
| Finance | 37 | 5 | 13.5% |

**Tenure and age**

| Tenure | Attrition rate | Age group | Attrition rate |
|---|---|---|---|
| 0-2 yrs | 32.4% | <30 | 33.0% |
| 3-5 yrs | 25.0% | 30-39 | 22.5% |
| 6-10 yrs | 18.0% | 40-49 | 24.8% |
| 10+ yrs | 17.8% | 50+ | 16.7% |

**Income and job satisfaction**

| Monthly income | Attrition rate | Job satisfaction | Attrition rate |
|---|---|---|---|
| Below 5,000 | 39.3% | 1 | 42.4% |
| 5,000-6,999 | 26.2% | 2 | 27.2% |
| 7,000-8,999 | 19.1% | 3 | 20.7% |
| 9,000 and above | 6.2% | 4 | 18.5% |

- Employees with a satisfaction score of 1-2 leave at 34.0%, compared with 19.8% for scores of 3-4.
- Attrition shows no clear pattern by commute distance (24.3% for 1-10 km, 25.6% for 11-20 km, 25.2% for over 20 km).
- Male employees show a higher attrition rate (28.7%) than female employees (20.9%).
- The income band above 9,000 contains only 16 employees and the 50+ age group only 30, so their rates are less stable.

**Employees who left versus stayed**

| Metric | Left | Stayed |
|---|---|---|
| Average age | 35.1 | 36.7 |
| Average tenure (years) | 4.1 | 5.3 |
| Median monthly income | 5,580 | 6,615 |
| Average job satisfaction | 2.42 | 2.84 |
| Average commute distance (km) | 14.6 | 14.7 |

## Business recommendations

These are hypotheses for further measurement or pilot programs, not claims of proven impact.

1. Review overtime workload and test overtime limits or compensation adjustments, starting with Sales and R&D, since overtime is associated with the largest gap in attrition.
2. Introduce structured onboarding and check-ins during the first two years, when attrition is highest.
3. Review pay competitiveness for employees earning below 5,000 per month, who leave at the highest rate among income bands.
4. Follow up on low job satisfaction scores (1-2) with short surveys and manager conversations, and track whether attrition changes.
5. Investigate working conditions in the Sales department, which has the highest attrition among departments with at least 30 employees.
6. Do not prioritize commute distance, as it shows no clear association with attrition in this dataset.

## Power BI dashboard

The dashboard is built from `HR_Attrition_Cleaned.csv` and includes KPI cards (Total Employees, Employees Left, Attrition Rate %), attrition rate by department, overtime, tenure group and age group, and slicers for Department and Gender.

![HR Employee Attrition Dashboard](HR%20Employee%20Attrition%20Analysis.png)

## Repository files

| File | Description |
|---|---|
| `HR Employee Attrition Analysis.pbix` | Power BI dashboard |
| `HR Employee Attrition Analysis.png` | Dashboard screenshot |
| `HR_Attrition_Cleaned.csv` | Cleaned synthetic dataset |
| `HR_Employee_Attrition_Analysis.ipynb` | Python analysis notebook (in Vietnamese) |
| `README.md` | Project documentation |

## How to run in Google Colab

1. Download `HR_Employee_Attrition_Analysis.ipynb` and `HR_Attrition_Cleaned.csv`.
2. Open Google Colab → File → Upload notebook, and select the notebook.
3. Open the Files panel on the left and upload `HR_Attrition_Cleaned.csv` to the session storage.
4. Select Runtime → Run all.
5. Review the data validation, KPIs, charts and insights.

If the CSV has missing required columns or invalid values, the notebook raises a descriptive error.

## Limitations

- The dataset is synthetic; results illustrate the workflow and are not real HR findings.
- The analysis is descriptive. Associations between factors and attrition do not establish causation, and factors such as overtime, income and satisfaction may be related to each other.
- The data is a single snapshot without exit dates, so trends over time cannot be analyzed.
- Some groups are small (for example HR with 34 employees), so their rates can vary considerably.
- The dataset has no information on reasons for leaving, compensation policy or labor market conditions.
