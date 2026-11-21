# patient-recovery-analysis-hcl
PROJECT DOCUMENTATION
Patient Recovery Analysis Using Python
Console-Based Hospital Recovery Data Processing in Google Colab
**1. Introduction**
Patient Recovery Analysis is a console-based Python project that loads and processes hospital
recovery records from a CSV file ( patient_recovery_dataset.csv ). Using foundational Python
constructs and Pandas, it cleans missing and duplicate entries, labels stay tiers and risk levels,
summarizes outcomes, and saves cleaned outputs without visual charts.

**2. Objectives of the Project**
To understand how Python works with tabular hospital datasets.
To load and process CSV files using Pandas and core Python structures.
To clean duplicate rows and missing values in numeric and text columns.
To classify stay duration and risk levels using functions, loops, and conditionals.
To understand clinical markers such as Bilirubin and Albumin in recovery data.
To export cleaned records and summary results to text and CSV files.

**3. Technologies Used**
Programming Language: Python
Libraries: Pandas, NumPy
Platform: Google Colab
Dataset Format: CSV ( patient_recovery_dataset.csv )
Key Columns: Patient_ID , Age , Sex , Department , Admission_Type ,
Length_of_Stay_Days , Bilirubin , Albumin , Recovery_Score , Recovery_Status

**4. Working of the Code**
Step 1 — Load Dataset: Reads patient_recovery_dataset.csv using pd.read_csv() into a
DataFrame (with fallback support if uploaded via Colab files or raw GitHub URL).
Step 2 — Clean Data ( clean_data ): Removes duplicate rows (reducing 121 rows to 120 unique
patient records), fills missing numbers with the column median, and fills missing text values with
"Unknown" .
Step 3 — Add Labels ( add_labels ): Uses loops and if/elif/else conditions to assign
Stay_Group ( Short for ≤ 6 days, Medium for 7–12 days, Long for > 12 days) and Risk_Level
( Low Risk , Moderate Risk , High Risk ) from Bilirubin (liver stress indicator; higher values ≥ 2.5
add risk), Albumin (blood plasma protein indicator; lower values < 3.2 add risk), and
Length_of_Stay_Days (≥ 14 days adds risk).
Step 4 — Summarize & Export ( show_summary ): Counts recovery statuses via a dictionary,
prints group averages by Recovery_Status plus a Total Avg line across all patients, finds overlap
between High Risk and Long stay patients using a set intersection, and saves
cleaned_patient_data.csv and summary.txt .


**5. Software Development Life Cycle (SDLC)**
Phase 1 — Planning: Plan a concise, syllabus-aligned Python script to clean and summarize
hospital recovery records in the console without external visualization libraries.
Phase 2 — Requirement Analysis: Hardware: laptop or computer with internet access. Software:
Python, Google Colab, Pandas, NumPy, and patient_recovery_dataset.csv .
Phase 3 — System Design: Input: patient_recovery_dataset.csv . Processing: duplicate
removal, median/text imputation, stay/risk labeling, dictionary status counts, group and total
averages, and set overlap. Output: console summary, cleaned_patient_data.csv , and
summary.txt .
Phase 4 — Implementation: Implemented modular Python functions ( clean_data ,
add_labels , show_summary ) using lists, dictionaries, sets, loops, conditionals, and Pandas
DataFrames.
Phase 5 — Testing: Verified duplicate removal (121 to 120 rows), median imputation on missing
values, dictionary status counts (95 Recovered, 17 Extended Care, 8 Readmitted (30d)), group and
total averages, set intersection (19 overlapping patients), and file export; also tested
FileNotFoundError when the CSV is missing from the working folder.
Phase 6 — Deployment: Executed in Google Colab with patient_recovery_dataset.csv placed
in the working directory or committed separately in the GitHub repository.
Phase 7 — Maintenance: Extendable by updating dataset records, adjusting risk thresholds,
adding department or admission-type breakdowns, or expanding summary metrics.

**6. Expected Output**
Deduplicated count of 120 unique patient records (from 121 raw rows).
Dictionary counts for Recovery_Status : Recovered (95), Extended Care (17), and Readmitted
(30d) (8).
Group averages by Recovery_Status and the overall Total Avg line (Stay: 9.42 days, Bilirubin:
2.43, Albumin: 3.50, Recovery Score: 81.35).
Set overlap showing 19 patients who are both High Risk and Long stay.
Saved output files: cleaned_patient_data.csv and summary.txt .

**7. Advantages**
Simple, readable structure suited to beginners learning Python and Pandas.
Handles missing values and duplicate rows before analysis.
Demonstrates dictionaries, sets, loops, conditionals, and file output clearly.
Produces both console output and saved CSV/text files.

**8. Limitations**
Requires patient_recovery_dataset.csv to be available in the active working directory.
Uses simple rule-based thresholds rather than clinical diagnosis models.
Does not include data visualization charts.
Patient Recovery Analysis — Project Documentation Page 2 of 3

**9. Future Scope**
Department-wise and admission-type recovery comparisons.
Additional lab markers and configurable risk rules.
Testing on additional hospital or recovery CSV datasets.

**10. Conclusion**
The Patient Recovery Analysis project demonstrates practical data cleaning, feature labeling,
dictionary and set operations, and file export in Python using Pandas. It provides a clear foundation
for structured data analysis in academic and training projects.

**11. Dataset File**
Separate dataset file: patient_recovery_dataset.csv (also available as
patient_recovery_dataset.xlsx ). Upload or commit it to the repository/working directory before
running the script.
