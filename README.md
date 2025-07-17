# Bank Transaction Analysis

This project analyzes transaction patterns in a bank dataset to uncover meaningful insights related to fraud detection, user behavior, and transaction categorization.

---

##  Dataset Used

The analysis is based on the **`bs140513_032310.csv`** dataset, a public dataset commonly used for fraud detection. It includes features like transaction `amount`, `step` (hourly timestamp), user IDs, origin/destination, transaction type, and a binary label `isFraud`.

---

##  Analysis Overview

The notebook walks through a series of visual and statistical explorations. Below is a summary of each major component of the analysis:

---

###  1. Distribution of Transaction Amounts and Amount Bins

- The transaction amounts are divided into three bins:
  - **L (Low):** 0–49.99 €
  - **M (Medium):** 50–199.99 €
  - **H (High):** 200 € and above
- A histogram is plotted to show the distribution, along with vertical red lines to indicate bin boundaries.
- Helps identify skewness and clustering of transaction amounts.

---

###  2. Distribution by Time-of-Day

- Extracts the hour of the day from the `step` variable using modulo operation (`step % 24`).
- Creates time-of-day bins:
  - **N (Night):** 00:00–05:59
  - **M (Morning):** 06:00–11:59
  - **E (Evening):** 12:00–17:59
  - **N2 (Night 2):** 18:00–23:59
- Visualizes the count of transactions occurring in each time bin.

---

###  3. Symbol Alphabet Size

- The number of unique values (alphabet size) is calculated for selected categorical columns:
  - `type`, `nameOrig`, `nameDest`, `amt_bin`, `tod_bin`
- This helps assess cardinality and understand encoding complexity for machine learning.

---

##  Key Insights

- Most transactions fall under the **Low (L)** bin.
- There is a consistent pattern in transaction frequency by time-of-day.
- Some user IDs and transaction types show high uniqueness, indicating possible synthetic or anonymized data.
