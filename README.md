# 🏦 Bank Loan Analytics Dashboard — Power BI + SQL

An interactive **Bank Loan Performance Dashboard** built using **SQL** for data analysis and **Power BI** for visualization.  
This project tracks key lending metrics, analyzes loan quality (Good vs Bad Loans), and provides insights into borrower trends to support data-driven financial decision-making.

---

## 📘 Project Overview

The **Bank Loan Analytics Dashboard** transforms raw loan data into actionable insights.  
It combines SQL-driven KPI calculations with Power BI’s visual storytelling to help stakeholders evaluate loan performance, monitor risk, and optimize portfolio management.

**Key Objectives:**
- Evaluate loan performance using key indicators  
- Compare **Good vs Bad Loans**  
- Track trends across **Month, State, Purpose, Employment Length, Term, and Ownership**  
- Build a dynamic, interactive Power BI dashboard for financial analysis

---

## ⚙️ Tools & Technologies

| Tool / Technology | Purpose |
|--------------------|----------|
| **SQL (MySQL / SQL Server)** | Data extraction, cleaning, and KPI computation |
| **Power BI Desktop** | Dashboard design and data visualization |
| **CSV Dataset** | Source data for analysis |
| **GitHub** | Version control and portfolio publishing |

---

## 🧩 Dataset Overview

Dataset: **`financial_loan.csv`**

| Column | Description |
|---------|--------------|
| `id` | Unique loan identifier |
| `loan_status` | Loan state (Fully Paid, Current, Charged Off) |
| `loan_amount` | Total amount funded |
| `total_payment` | Amount received from borrowers |
| `int_rate` | Interest rate (%) |
| `dti` | Debt-to-income ratio |
| `purpose` | Loan purpose (education, home, car, etc.) |
| `emp_length` | Employment length (years) |
| `address_state` | Borrower’s state |
| `term` | Loan term (36 or 60 months) |
| `issue_date` | Date loan was issued |

---

## 📊 Key Performance Indicators (KPIs)

| KPI | Value | Description |
|------|-------|-------------|
| **Total Loan Applications** | 38.6K | Total number of loans issued |
| **Total Funded Amount** | \$435.8M | Total loan amount distributed |
| **Total Amount Received** | \$473.1M | Total repayments collected |
| **Average Interest Rate** | 12.0% | Mean loan interest rate |
| **Average DTI** | 13.3% | Mean borrower debt-to-income ratio |
| **Good Loan %** | 86.2% | Fully Paid or Current loans |
| **Bad Loan %** | 13.8% | Charged Off loans |

---

## 🧮 SQL Analysis Summary

### 1️⃣ Loan KPIs
```sql
-- Total Applications
SELECT COUNT(id) AS Total_Applications FROM bank_loan_data;

-- Total Funded Amount
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data;

-- Total Amount Received
SELECT SUM(total_payment) AS Total_Amount_Collected FROM bank_loan_data;

-- Average Interest Rate & DTI
SELECT AVG(int_rate)*100 AS Avg_Int_Rate, AVG(dti)*100 AS Avg_DTI FROM bank_loan_data;
