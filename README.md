# BigMart Sales Prediction (XGBoost)

## Project Background

BigMart operates multiple retail outlet formats across different locations and store sizes.  
Accurately forecasting product-level sales is critical for **pricing strategy, outlet planning, and inventory decisions**.

In practice:
- Sales vary significantly across outlets
- Price, visibility, and outlet characteristics interact in **non-linear ways**
- Traditional linear models struggle to capture real consumer behavior

This project answers a core business question:

**“Given product and outlet characteristics, what level of sales should we realistically expect per outlet?”**

---

## Project Highlights

- Built an end-to-end retail sales prediction pipeline (EDA → Modeling)
- Used Linear Regression as a baseline and XGBoost for non-linear patterns
- XGBoost reduced RMSE by ~50% compared to Linear Regression
- Outlet characteristics were stronger sales drivers than product attributes
- Estimated realistic expected sales of **~2,500 per outlet**

**Tools:** Python  
**Environment:** Jupyter Notebook (Google Colab)  
Notebook: [View Here](https://github.com/SethSterlin/BigMart-Sales-Prediction/blob/main/Big_Mart_Project.ipynb)

---

## Dataset Overview

- **Records:** 8,523  
- **Features:** 13  
- **Target:** `Item_Outlet_Sales`

**Key Feature Groups**
- Product: Item MRP, Visibility, Weight, Category
- Outlet: Type, Size, Location, Establishment Year

---

## Exploratory Insights

- **Outlet Type is the strongest sales driver**, especially Supermarket Type 1 & 3
- **Medium-sized outlets outperform** small and large outlets on average
- Pricing shows **non-linear demand behavior**
- Visibility has a positive but secondary impact

These insights justify the use of **tree-based models**.

---

## Modeling Approach

### Baseline: Linear Regression
- Simple and interpretable
- Performs poorly on high-sales outlets
- Test R² = **-0.53**, RMSE ≈ **2,174**

### Advanced Model: XGBoost
- Captures non-linear effects and feature interactions
- Robust to skewed sales distributions
- Test R² = **0.58**, RMSE ≈ **1,138**

---

## Key Drivers of Sales (XGBoost)

Top contributors:
1. Outlet Type (Supermarket formats)
2. Outlet Size (Medium)
3. Item MRP
4. Outlet Location
5. Item Visibility

**Executive Insight:**  
*Where a product is sold matters more than the product itself.*

---

## Sales Prediction (New Product Scenario)

**Scenario:**  
Snack food, MRP ≈ 150, medium outlet, Tier 2, Supermarket Type 1

**Predicted Sales**
- Linear Regression: **2,622.85**
- XGBoost: **2,526.07**

---

## Executive Summary

- Both models agree on expected sales ≈ **2.5K per outlet**
- XGBoost is more reliable due to superior test performance
- **~2,500** should be used as a baseline forecast
- > 2,600 indicates outperformance
- < 2,300 suggests potential underperformance

**Bottom Line:**  
**Executives should reasonably expect ~2.5K sales per outlet, with XGBoost as the decision-grade model.**
