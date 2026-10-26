# employee-turnover-excel-dashboard
Interactive Excel dashboard analyzing employee turnover (11,991 employees after removing 3,008 duplicate rows) with PivotTables, PivotCharts, and slicers. Key finding: low-salary employees left at 20.5% vs 4.8% for high-salary, and leavers had much lower satisfaction (0.44 vs 0.67).

# Employee Turnover Dashboard (Excel)

## Overview
An interactive Excel dashboard analyzing employee turnover across 11,991 employees. 
It uses PivotTables, PivotCharts, and slicers to show who leaves, and how pay, 
satisfaction, workload, and promotion relate to leaving.

## Business Questions
1. What share of employees leave?
2. Does turnover differ by department?
3. Is pay related to who leaves?
4. How do leavers differ from stayers on satisfaction and workload?
5. Does a recent promotion relate to staying?

## Dataset
HR employee turnover dataset (`HR_comma_sep.csv`), 14,999 rows and 10 columns: 
satisfaction level, last evaluation, number of projects, average monthly hours, 
years at company, work accident, left (yes/no), promotion in last 5 years, 
department, and salary band (low/medium/high).
Source: [add link to the original dataset page]

## Data Cleaning
- **Removed 3,008 exact duplicate rows (20.1% of the file)**, leaving 11,991 unique 
  records. The dataset has no employee ID, so these were identified by matching on 
  all 10 fields, which is unlikely to happen by chance.
- Checked for missing values: none found.
- Renamed awkward columns (e.g. `average_montly_hours` to `average_monthly_hours`).
- Kept the original data on a separate "Raw Data" sheet, untouched.
- Built PivotTables from the bounded Table range rather than full columns, so no 
  phantom "(blank)" categories appear in the PivotTables or slicers.

## Dashboard Contents
| View | Question answered |
|---|---|
| Turnover Overview | Share of employees who left |
| Turnover by Department | Which departments lose the most people |
| Turnover by Salary Level | How pay band relates to leaving |
| Satisfaction & Hours | How leavers differ from stayers |
| Turnover by Promotion | Whether recent promotion relates to staying |

Slicers (Department, Salary, Left) filter every view at once.

## Key Findings
- **16.6% of employees left** (1,991 of 11,991).
- **Pay is the strongest pattern.** Low-salary employees left at **20.5%**, medium at 
  14.6%, and high at just **4.8%**. Low-salary employees made up about 59% of everyone 
  who left.
- **Department matters less than pay.** HR had the highest turnover (18.8%) and 
  Management the lowest (11.9%), a 7-point spread, compared with a 16-point spread 
  across salary bands.
- **Leavers were much less satisfied.** Average satisfaction was **0.44 for leavers vs 
  0.67 for stayers.**
- **Leavers worked more.** They averaged 208 hours a month vs 199 for stayers 
  (about 9 more).
- **Leavers weren't weaker performers.** Average last evaluation was 0.72 for both groups.
- **Promotion is rare and linked to staying.** Only 203 employees (1.7%) were promoted 
  in the last 5 years; 3.9% of them left, vs 16.8% of those not promoted.

## Recommendations
- **Review pay in the low-salary band first.** It holds the highest turnover (20.5%) 
  and most of the people who left.
- **Use satisfaction as an early warning signal.** A drop in satisfaction scores 
  could trigger a check-in before someone resigns.
- **Monitor workload.** Leavers worked more hours on average, so sustained high hours 
  may be a risk factor.
- **Do not assume low performers are the ones leaving.** Since evaluation scores were 
  identical for leavers and stayers, turnover here is costing the company people who 
  were rated just as well as those who stayed.
- **Look at promotion pathways.** Very few employees get promoted, and those who do 
  are far less likely to leave.
- **Fix the data source.** A 20% duplicate rate suggests a problem in how the data is 
  exported or recorded.

## Limitations
- This is a widely used public dataset and likely anonymized or synthetic. Findings 
  describe patterns in this data, not any specific company.
- The data is a snapshot with no dates, so it can't show when people left or how 
  satisfaction changed over time.
- These are correlations, not causes. For example, low satisfaction may be a reason 
  for leaving or a result of already planning to leave.
- Only 203 employees were promoted, so the promotion comparison rests on a small group.

## Tools Used
Microsoft Excel: PivotTables, PivotCharts, Slicers, COUNTIFS/AVERAGEIFS formulas

## Repository Contents
- `Employee_Turnover_Dashboard.xlsx`: full workbook (raw data, cleaned data, PivotTables, dashboard)
- `screenshots/`: dashboard and individual chart images

## How to Use
Download the workbook and open it in Excel. Click the slicers on the Dashboard sheet 
to filter all charts at once.
