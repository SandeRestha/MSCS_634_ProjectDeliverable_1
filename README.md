# Walmart Sales Data Analysis — Deliverable 1

## Dataset Summary
This project uses the **Walmart Sales** dataset from [Kaggle](https://www.kaggle.com/datasets/mikhail1681/walmart-sales), containing weekly sales data from multiple Walmart stores across the U.S.  

**Key Columns:**
- `Store`, `Date`, `Weekly_Sales`, `Holiday_Flag`, `Temperature`, `Fuel_Price`, `CPI`, `Unemployment`  
- Thousands of rows with 8+ attributes (meets project size and attribute requirements)

**Why this dataset?**
- Combines **temporal**, **economic**, and **categorical** variables  
- Reflects real-world retail behavior influenced by both internal and external factors  
- Ideal for regression, classification, and clustering analyses  

---

## Key Insights from Analysis
- **Sales Distribution:** `Weekly_Sales` is **right-skewed**, meaning most weeks have moderate sales while holiday weeks spike sharply.  
- **Macro Trends:** Economic variables (`CPI`, `Fuel_Price`, `Unemployment`) vary smoothly but have **weak direct correlation** with sales.  
- **Relationships:** Pairplots and regressions confirm numeric features alone don’t explain sales; seasonal and store-level patterns are likely key.  
- **Economic Context:** A moderate negative link (≈ –0.28) between `CPI` and `Unemployment` mirrors expected macroeconomic patterns.  

---

## Data Cleaning & Exploration Steps
1. **Formatting:**  
   Trimmed text spaces, parsed the `Date` column to datetime, and enforced numeric datatypes for metrics.  
2. **Handling Missing Values:**  
   - Numeric → replaced with **median**  
   - Categorical → replaced with **mode**  
3. **Duplicates:**  
   Removed duplicate store-week records.  
4. **Outlier Treatment:**  
   Applied **IQR capping** to reduce the influence of extreme values without deleting valid entries.  
5. **EDA Techniques:**  
   - Histograms & KDEs → explored distributions  
   - Boxplots → verified spread after capping  
   - Correlation Heatmap → checked numeric relationships  
   - Pairplots & Regression → visualized variable interactions  

---

## Challenges & Solutions
| Challenge | Solution |
|------------|-----------|
| `Weekly_Sales` scale dominated other variables | Plotted individually and used normalized views for comparison |
| Weak numeric correlations | Identified need for feature engineering — add holidays, store IDs, and time features |
| Outliers in CPI & sales | Used **IQR capping** to maintain data integrity instead of removing rows |

---
