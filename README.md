# airline-customer-segmentation-hierarchical-clustering
Unsupervised customer segmentation of frequent flyer mileage data using Hierarchical Clustering and dendrogram analysis to optimize targeted marketing campaigns.

# Airline Customer Segmentation using Hierarchical Clustering

## 1. Business Problem
### 1.1. Business Objective
The goal is to analyze customer frequent flyer data (`EastWestAirlines.xlsx`) to identify natural groupings (clusters) of passengers. This allows the airline to design targeted marketing strategies, VIP loyalty programs, and personalized promotional offers for high-value customer segments.
### 1.2. Constraints
* Outliers in flight miles or balance can skew distance calculations; robust scaling and linkage criteria selection are critical.
* Interpretability of clusters is essential for marketing teams to act on insights effectively.

## 2. Data Dictionary
| Feature Name | Data Type | Description |
| --- | --- | --- |
| `ID` | Integer | Unique identifier for the flight passenger |
| `Balance` | Numerical | Number of miles eligible for award travel |
| `Qual_miles` | Numerical | Number of miles counted as qualifying for top flight status |
| `cc1_miles` / `cc2_miles` / `cc3_miles` | Categorical/Ordinal | Miles earned with freq. flyer credit card under banner 1, 2, & 3 |
| `Bonus_miles` | Numerical | Miles earned from non-flight bonus transactions in the past year |
| `Bonus_trans` | Numerical | Number of non-flight bonus transactions in the past year |
| `Flight_miles_12mo` | Numerical | Number of flight miles in the past 12 months |
| `Flight_trans_12` | Integer | Number of flight transactions in the past 12 months |
| `Days_since_enroll` | Numerical | Number of days since customer enrolled in the frequent flyer program |
| `Award` | Binary (0/1) | Indicator whether the user had a free award flight linkage |

## 3. Data Pre-processing
* **Data Cleaning:** Checked for missing values, handled unique identifiers, and filtered out irrelevant ID columns.
* **Feature Engineering & Normalization:** Applied standard scaling (`StandardScaler` or `MinMaxScaler`) since features like `Balance` and `Bonus_miles` have drastically different magnitudes compared to counts and binary indicators.

## 4. Exploratory Data Analysis (EDA)
* **Summary:** Statistical summary of mileage accumulation, account age, and transaction frequency across the customer base.
* **Univariate Analysis:** Distribution plots (histograms and boxplots) for numerical variables such as `Balance` and `Days_since_enroll` to identify right-skewness.
* **Bivariate Analysis:** Scatter plots and correlation heatmaps between mileage earned and bonus transactions.

## 5. Model Building
* **5.1 Scaled Data & Multiple Options:** Built hierarchical models using different linkage criteria (Ward, Complete, Average) and distance metrics (Euclidean).
* **5.2 Dendrogram Visualization:** Plotted and analyzed dendrograms to determine the optimal number of clusters visually.
* **5.3 Cluster Validation & Insights:** Cut the dendrogram at optimal thresholds (e.g., 4 to 5 clusters), profiled each cluster's centroid values, and derived actionable behavioral traits (e.g., "High-Value Frequent Fliers" vs. "New Low-Activity Users").

## 6. Business Benefits & Impact
* Enables precision marketing, reducing promotional spend wastage on inactive customers.
* Enhances customer lifetime value (LTV) through personalized rewards and VIP tier upgrades.
