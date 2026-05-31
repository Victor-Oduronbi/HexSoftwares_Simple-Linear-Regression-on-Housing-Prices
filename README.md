# Simple-Linear-Regression-on-Housing-Prices

An internship project focused on implementing a end-to-end Machine Learning workflow to predict housing prices using linear regression models. 

## 📋 Task Overview
The goal of this project is to apply core data science foundations to analyze and build a predictive model for housing markets. The primary assignment milestones include:
* **Dataset Utilization:** Migrating from legacy datasets to the modern California Housing framework.
* **Data Preprocessing:** Executing programmatic feature selection and handling mathematical feature scaling.
* **Model Pipeline:** Constructing and evaluating a Multiple Linear Regression model.
* **Exploratory Analysis:** Using correlation heatmaps to justify feature influence.

---

## 🗂️ Dataset Glossary & Features
The dataset contains aggregated data from the 1990 U.S. Census, where each row represents a distinct census block group.

1. `MedInc`- Median Income
2. `HouseAge`- Median House Age
3. `AveRooms`- Average Rooms
4. `AveBedrms`- Average Bedrooms
5. `Population`- Block Population
6. `AveOccup`- Average Occupancy
7. `Latitude`- Latitude
8. `Longitude`- Longitude
9. `MedHouseVal`- Median House Value (Target)

---

## ⚙️ Data Preprocessing & Methodology

### 1. Feature Selection
To avoid overwhelming the linear framework with raw demographic counts, structural and economic markers (`MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`) were programmatically isolated as predictors for the target market price (`MedHouseVal`).

### 2. Normalization & Standardization
To prevent high-magnitude features (e.g., populations in thousands) from mathematically dominating low-magnitude metrics (e.g., average bedroom counts), Scikit-Learn's `StandardScaler` was used. This shifted features to a shared standard normal distribution:
$$\mu = 0, \sigma = 1$$

---

## 📈 Key Insights & Correlation Analysis
<p align="center">
  <img width="943" height="790" alt="image" src="https://github.com/user-attachments/assets/97928e20-8bea-4267-aeb8-affedfb33fa1" />
</p>


Using a Seaborn correlation heatmap matrix, the following foundational insights were observed:
* **Primary Economic Driver:** Median Income (`MedInc`) exhibits the strongest positive linear relationship with housing prices (~0.69), proving neighborhood wealth is the baseline driver of property premiums.
* **Multicollinearity:** Structural features like `AveRooms` and `AveBedrms` display a high internal correlation with each other, meaning they introduce redundant structural attributes to a linear equation.
* **Geographic Trends:** Negative coordinate correlations (`Latitude`/`Longitude`) capture regional real estate dynamics, tracking premium valuations near major coastal economic clusters.

---

## 📊 Model Evaluation Results

The baseline Multiple Linear Regression model yielded the following validation metrics:


| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **R-squared ($R^2$) Score** | `0.5099` | The model explains roughly 51% of the price variance. |
| **RMSE** | `0.8014` | The average prediction error translates to roughly **$80,140**.* |

*\*Note: The target variable is scaled in hundreds of thousands of dollars ($100,000).*

---

## 🚀 Future Enhancements
To build upon these baseline linear metrics, future updates to this repository will explore:
1. **Outlier Filtering:** Dropping artificially capped values ($500k ceiling) to stabilize linear lines of best fit.
2. **Feature Engineering:** Crafting derived data columns such as *Rooms Per Person* (`AveRooms` / `AveOccup`).
3. **Non-Linear Models:** Implementing tree-based architectures like `RandomForestRegressor` to map localized pricing mechanics.
