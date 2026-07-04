# 🏥 Hospital Management Data Analytics

Welcome to the **Hospital Management Data Analytics** project! This project focuses on cleaning, analyzing, and deriving actionable business insights from a messy hospital dataset using Python.

[![LinkedIn](https://img.shields.io/badge/Connect_on-LinkedIn-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/harshvardhan-gholap-821255326/)

## 🛠️ Tech Stack Used
*   **Pandas:** For data manipulation, cleaning, and transformation.
*   **NumPy:** For statistical analysis and numerical operations.
*   **Matplotlib:** For creating impactful data visualizations.

---

## 🎯 Problem Statement
The hospital had 5 different CSV files (`Patients`, `Doctors`, `Appointments`, `Medicines`, `Billing`) containing messy, real-world data:
*   **Duplicate Rows:** Identical records appearing multiple times.
*   **Missing Values:** Empty fields in crucial columns like `Age`, `City`, `Fees`, `Price`, and `TotalAmount`.
*   **Inconsistent Text & Whitespace:** e.g., `" Mumbai "` vs `"mumbai"`.
*   **Invalid Values:** Negative ages or negative billing amounts.
*   **Inconsistent Date Formats:** Dates stored in various unstandardized formats.

**The Risk:** Directly analyzing this messy data would lead to flawed insights (e.g., duplicate rows could artificially double the reported revenue, or ignoring missing ages could skew demographic analysis).

---

## 🔧 Solution & Methodology

| Step | What was done | Why it was done |
| :--- | :--- | :--- |
| **Data Cleaning** | Used `drop_duplicates()`, `fillna()`, `.str.strip()`, and handled invalid values by converting them to `NaN`. | To ensure data accuracy and prevent skewed metrics. |
| **Smart Filling** | Filled missing `Fees`/`Price` using department-wise or medicine-wise averages instead of the overall average. | Because a Cardiology consultation fee differs from Dermatology; an overall average would misrepresent the data. |
| **Data Transformation** | Created custom columns like `AgeGroup`, `HighValueBill` flag, and extracted `Month`/`Weekday` from dates. | To create new dimensions required for in-depth, business-ready analysis. |
| **Data Merging** | Merged 5 files into a single `master_df` using `merge()` (kept Medicines separate for specific analysis). | To analyze correlations between Patients, Doctors, Billing, and Appointments holistically. |
| **EDA & Statistics** | Utilized `groupby()`, `value_counts()`, `np.mean()`, and `np.corrcoef()`. | To uncover hidden patterns and trends within the data. |
| **Visualization** | Designed Bar, Line, Pie, and Scatter charts. | To translate raw numbers into easily understandable, visual patterns. |

---

## 💡 How Insights Were Derived (The Process)

Finding true insights goes beyond just printing numbers. It follows a distinct pattern:
**Observe Fact → Compare → Connect → Suggest Action**

**Real Project Example:**
1.  **Fact 1:** Running `groupby('Department')['TotalAmount'].sum()` revealed that **Cardiology** generated the highest revenue (₹3.78 Lakhs).
2.  **Fact 2:** Filtering by `Status == 'Cancelled'` showed that Cardiology also had the highest number of appointment cancellations (53).
3.  **The Connection:** Combining these facts led to a realization: "The department generating the most revenue is also experiencing the highest cancellation rate. This represents a significant loss!"
4.  **The Insight:** Cardiology is the most valuable department for the hospital, but operational inefficiencies (like scheduling or long wait times) are causing a loss in potential revenue.
5.  **Suggested Action:** The hospital should optimize staffing and scheduling for the Cardiology department to reduce wait times and cancellations.

---

## 📌 Project Summary
> *"We took messy hospital data, transformed it into a clean, structured, and analysis-ready format using Pandas and NumPy. We then discovered hidden patterns, visualized them with Matplotlib, and connected multiple findings to generate data-backed, business-relevant insights that can drive real-world hospital decision-making."*

### 📋 Key Milestones Achieved
*   ✅ **Data Loading & Understanding**
*   ✅ **Data Cleaning** (Duplicates, nulls, whitespaces, invalid values)
*   ✅ **Data Transformation** (Age Groups, High-Value Flags, Time features)
*   ✅ **Data Merging** (3-step complex merge strategy)
*   ✅ **Exploratory Data Analysis (EDA)**
*   ✅ **NumPy Statistical Analysis** (Mean, median, std, IQR)
*   ✅ **Visualizations** (Bar, line, hist, pie, scatter)
*   ✅ **Business Insights** (6 data-backed insights, including cross-insights)