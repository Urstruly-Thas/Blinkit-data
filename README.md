# Blinkit Grocery Sales Analysis – Data Portfolio Project

## Project Background

This was my first end-to-end data analysis project, built to apply foundational skills I developed through self-learning, online courses, and a lot of late-night research. I wanted a dataset that was simple enough to explore thoroughly but rich enough to extract business insights. After reviewing several public datasets, I selected the **Blinkit Grocery Sales Dataset** from Kaggle for its balanced mix of product-level and outlet-level attributes.

This project documents not just the technical steps, but the thought process of a beginner analyst — from uncertainty to insight. My goal was to simulate the real-world data workflow: cleaning raw data, analyzing it for patterns, visualizing findings, and providing actionable recommendations.

## About the Dataset

The Blinkit Grocery Dataset is a simulated retail dataset comprising sales data from various grocery items across five store outlets. It includes:

- **Product-level data**: `Item_Identifier`, `Item_Weight`, `Item_Fat_Content`, `Item_Type`, `Item_MRP`, `Item_Visibility`
- **Outlet-level data**: `Outlet_Identifier`, `Outlet_Establishment_Year`, `Outlet_Size`, `Outlet_Location_Type`, `Outlet_Type`
- **Target variable**: `Item_Outlet_Sales`

The dataset is well-suited for exploratory analysis in retail, pricing strategy, customer behavior, and outlet performance.

## Tools Used

- **Excel**: Initial exploration and de-duplication
- **Python (Pandas, Seaborn, Matplotlib)**: Data cleaning, transformation, and EDA
- **Power BI**: Interactive dashboards and final storytelling

## Project Workflow

### 1. Data Cleaning

- Removed duplicates using Excel (`Data > Remove Duplicates`)
- Standardized inconsistent categorical entries (e.g., “Low Fat”, “low fat”, “LF”)
- Converted columns like `Item_MRP` and `Item_Outlet_Sales` to ₹ (rupees) for clarity
- Recast numerical columns (`Item_Weight`, `Item_Visibility`) as floats
- Used Python to drop NULLs and prepare a clean version of the dataset:

```python
import pandas as pd
df = pd.read_excel("Blinkit Grocery Data.xlsx")
df_cleaned = df.dropna()
df_cleaned.to_excel("Cleaned Blinkit Grocery Data.xlsx", index=False)
```

- Checked for outliers using `.describe()` and visualized key fields using boxplots

### 2. Data Analysis (Exploratory)

Performed EDA in Python using Pandas, Matplotlib, and Seaborn. Key questions explored:

- How many unique items and outlets are present?
- Which outlets perform the best and worst in sales?
- What are the top-selling and most profitable item categories?
- How do low-fat vs. regular products perform in sales?
- How does outlet size and type influence performance?
- Are there correlations between MRP, visibility, and sales?
- Does the year of outlet establishment affect sales?
- Which cities (locations) perform best?

Find the full Jupyter notebook [here](https://github.com/Urstruly-Thas/Blinkit-data/blob/main/data_analysis_of_blinkit_data.ipynb).

## Key Insights

- **Product Spread**: The dataset includes 1,535 unique products across 5 outlets.
- **Best Performing Outlet**: `OUT035` had the highest total sales. `OUT018` had the lowest.
- **Top-Selling Categories**: *Snack Foods* generated the most revenue; *Seafood* performed the worst.
- **Fat Content Trends**: Low-fat products outsold regular ones, hinting at health-conscious consumer behavior.
- **Outlet Size & Type**:
  - Small-sized outlets performed better than medium or high-sized ones.
  - Supermarket Type 1 outlets had the highest sales.
- **Pricing Uniformity**: Most item categories have an average MRP between ₹120–₹150.
- **Price vs. Visibility**: MRP showed moderate correlation with sales; visibility had little impact.
- **Outlet Age**: Stores opened before 2005 generated higher sales, suggesting that outlet maturity plays a role in customer trust and performance.

## Power BI Dashboard

An interactive Power BI dashboard was created to visually communicate the findings. It includes:

- KPIs: Total sales, average sales, item counts
- Visuals: Donut charts for fat content, bar charts for sales by outlet, size, item type
- Filters: Dynamic slicers by location, item type, outlet size

The dashboard layout emphasizes clarity, consistency, and guided storytelling for end users.

## Recommendations

1. **Highlight Health-Conscious Products**  
   Low-fat products outsold regular ones. Blinkit should promote healthy options prominently in-app, especially in metro areas.

2. **Expand What Works, Review What Doesn’t**  
   OUT035 and snacks are consistent performers. Blinkit should replicate this outlet model and consider repositioning or evaluating underperformers like OUT018.

3. **Leverage Established Outlets**  
   Outlets founded before 2005 had stronger sales. These could be targeted for loyalty programs or premium services.

4. **Focus on Small Store Formats**  
   Small-sized outlets had better turnover. Blinkit can prioritize this model for future expansion in dense urban locations.

## Conclusion

This project helped me understand that data analysis is more than just writing queries or code – it’s about asking meaningful questions and shaping insights from exploration. While the tools were important, the biggest learning came from building an end-to-end narrative from raw data to recommendations.

As a first portfolio project, this taught me the value of structure, iteration, and patience. It laid the groundwork for approaching more complex datasets in the future.

**PS:** This was my first full-cycle data analysis project. It may have areas for improvement, but it reflects my learning journey honestly and fully. I'm open to feedback and excited to keep building better analyses from here on.


