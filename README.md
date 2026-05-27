# Loan Default Risk Analysis Dashboard

### Dashboard Link : https://app.powerbi.com/groups/db313d07-c81d-41e7-a3da-81a06af67000/reports/d27351ab-a18e-4bc1-94e2-645df1a17eae/4c93ab0da78015007ad7?experience=power-bi

## Project Overview

This project is an interactive **Loan Default Risk Analysis Dashboard** developed using **Power BI** and **SQl Server** to analyze loan applicants, default risks, financial profiles, and lending trends.

The dashboard helps users understand:

* Loan default patterns
* Applicant demographics
* Credit score impact
* Employment and income analysis
* Loan distribution across categories
* Financial risk trends
* Year-over-Year (YOY) changes in loan amounts and defaults

The dashboard provides a clear visual representation of lending behavior and helps identify high-risk borrowers for improved risk assessment and decision-making.

---

## Project Objectives

* Analyze loan default behavior.
* Identify high-risk borrower segments.
* Monitor yearly default trends.
* Study applicant demographics and financial profiles.
* Analyze loan distribution across categories.
* Understand effects of employment, income, and credit scores.
* Support loan risk management and lending decisions.

---

## Tools & Technologies Used

* Power BI Desktop
* Microsoft Excel
* SQL Server
* DAX (Data Analysis Expressions)
* Power Query
* Data Visualization Techniques

---

## Dataset Information

The dataset contains:

* Applicant Age
* Age Group
* Credit Score
* Credit Score Category
* Income
* Income Category
* Employment Type
* Marital Status
* Education
* Loan Amount
* Loan Purpose
* Loan Term
* Default Status
* Debt-to-Income Ratio (DTI)
* Mortgage Information
* Dependents Information
* Loan Date
* Interest Rate

---

## Data Preparation Steps

### 1] Data Loading

Imported Excel dataset into **Power BI Desktop** from SQL Server.

Verified:

* Data types
* Column formats
* Relationships

---

### 2] Data Cleaning

Performed using **Power Query**:

* Removed missing values
* Checked duplicates
* Corrected data types
* Standardized categorical values
* Validated numerical fields

---

### 3] Age Group Creation

Created Age Group column for demographic analysis.

Example DAX:

```DAX
Age Group =
SWITCH(
TRUE(),
Loan_default[Age] <= 20,"Teen",
Loan_default[Age] <=45,"Adults",
Loan_default[Age] <=60,"Middle Age Adults",
"Senior Citizens"
)
```

---

### 4] Credit Score Category Creation

Created categories for risk segmentation.

Example DAX:

```DAX
Credit Score Category =
SWITCH(
TRUE(),
Loan_default[CreditScore] >=750,"High",
Loan_default[CreditScore] >=650,"Medium",
Loan_default[CreditScore] >=550,"Low",
"Very Low"
)
```

---

### 5] Income Category Creation

Example DAX:

```DAX
Income Category =
SWITCH(
TRUE(),
Loan_default[Income]>=100000,"High Income",
Loan_default[Income]>=50000,"Medium Income",
"Low Income"
)
```

---

## Dashboard Features

### 1] Loan Default & Overview Page

Dashboard displays:

* Loan Amount by Purpose
* Average Income by Employment Type
* Default Rate by Employment Type
* Average Loan Amount by Age Group
* Default Rate by Year

Purpose:

Monitor lending distribution and identify risky employment categories.

Examples:

Highest loan purpose contribution → Home Loans

Lowest default rate → Full-time Employees

Highest default rate → Unemployed Applicants

---

### 2] Applicant Demographics & Financial Profile

Visuals included:

* Median Loan Amount by Credit Score Category
* Loan Amount by Education Type
* Loan Distribution by Marital Status
* Mortgage & Dependents Analysis
* Number of Loans by Education Category

Helps analyze borrower demographics and financial characteristics.

---

### 3] Financial Risk Metrics Page

Risk analysis includes:

* YOY Loan Amount Change
* YOY Default Loan Change
* YTD Loan Amount
* Income Category Contribution
* Employment Type Contribution

This helps monitor yearly lending trends and risk fluctuations.

---

## Applicant Categories Used

### Age Groups

* Teen
* Adults
* Middle Age Adults
* Senior Citizens

---

### Credit Score Categories

* High
* Medium
* Low
* Very Low

---

### Income Categories

* High Income
* Medium Income
* Low Income

---

## Key Insights

### Home Loans Dominate Lending

Home loan purpose contributes the highest loan amount compared to:

* Business
* Education
* Auto
* Other

Thus, home loans represent the major lending segment.

---

### Employment Impacts Default Risk

Default rates show:

Unemployed → Highest risk

Part-time → Higher risk

Self-employed → Moderate risk

Full-time → Lowest risk

Thus, stable employment lowers default probability.

---

### Credit Score Influences Loan Distribution

Applicants with **high credit scores** receive larger loan amounts.

Lower credit score categories show increased financial risk.

---

### Adults Contribute Maximum Loans

Adults and middle-aged applicants account for the largest share of loans.

Teen applicants contribute the lowest average loan amount.

---

### Financial Risk Trends Vary Yearly

YOY analysis shows fluctuations in:

* Loan amount growth
* Default rates

Certain years experienced higher defaults while others showed recovery trends.

---

## Power BI Visuals Used

* KPI Cards
* Area Charts
* Line Charts
* Donut Charts
* Sankey Diagram
* Clustered Bar Charts
* Ribbon Charts
* Slicers

---

## DAX Measures Used

### Average Income

```DAX
Average Income =
AVERAGE(Loan_default[Income])
```

### Average Loan Amount

```DAX
Avg Loan Amount =
AVERAGE(Loan_default[LoanAmount])
```

### Default Rate

```DAX
Default Rate =
DIVIDE(
SUM(Loan_default[Default]),
COUNT(Loan_default[LoanID])
)*100
```

### YOY Loan Amount Change

```DAX
YOY Loan Amount Change =
[Current Year Loan] - [Previous Year Loan]
```

### YOY Default Change

```DAX
YOY Default Loan Change =
[Current Default] - [Previous Default]
```

---

## Dashboard Design Features

* Dark Theme UI
* Interactive Filters
* Multi-page Dashboard
* Dynamic Visuals
* Responsive Layout
* Year Filters
* Category Filters

---

## Business Benefits

This dashboard helps:

* Banks identify risky borrowers
* Financial institutions monitor defaults
* Risk teams analyze lending behavior
* Decision makers optimize approval strategies
* Analysts track financial risk trends

---

## Skills Demonstrated

* Data Cleaning
* Data Modeling
* Dashboard Design
* DAX Calculations
* Data Visualization
* Financial Data Analysis
* Risk Analytics
* Business Intelligence

---

## Conclusion

The **Loan Default Risk Analysis Dashboard** transforms raw loan data into meaningful business insights using Power BI. It helps analyze borrower profiles, monitor default trends, evaluate financial risks, and support better lending decisions.

The dashboard improves visibility into loan behavior and assists organizations in reducing financial risk through data-driven decision-making.
