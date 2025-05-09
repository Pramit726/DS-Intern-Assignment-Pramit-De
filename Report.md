# Equipment Energy Consumption Analysis – Brief Report

## 1. Approach to the Problem

The objective was to analyze energy consumption patterns and build a predictive model for **equipment energy consumption** using available environmental, operational, and temporal data.

### Key Steps:
- **Data Cleaning & Imputation**:  
  - MCAR missing values were handled using **median imputation** for numerical features.
- **Feature Engineering**:  
  - Extracted `hour` from the `timestamp` and categorized it into four time segments: **Morning, Afternoon, Evening, and Night**.
- **Preprocessing Pipeline**:  
  - Created a `Pipeline` using `ColumnTransformer` to:
    - Standardize numerical features
    - One-hot encode categorical variables (like `time_of_day`)
- **Modeling**:  
  - Used regression models such as **RandomForestRegressor**, **GradientBoostingRegressor**, and **LinearRegression** for initial benchmarking.
- **Evaluation Metrics**:  
  - Evaluated models using **R² Score**, **MAE**, and **RMSE**.

---

## 2. Key Insights from the Data

- **Lighting Energy** was one of the strongest predictors of equipment energy usage.

- External environmental conditions (e.g., **dew point, visibility, wind speed**) had relatively weaker influence but contributed marginally to prediction accuracy.
- The `random_variable1` and `random_variable2` fields had low correlation with target and were excluded in experiments.

---

## 3. Model Performance Evaluation

| Model                   | R² Score | RMSE  | MAE  |
|-------------------------|----------|-------|------|
| Linear Regression       | 0.05     | 127.70  | 70.09 |
| Decision Tree Regressor | -1.39    | 202.03 | 85.92 |
| Random Forest Regressor | 0.10      | 123.78  | 67.09  |
| Gradient Boosting       | 0.07    | 125.91  | 69.00  |


---

#### 4. Recommendations for Reducing Equipment Energy Consumption

> **Observation**: The current task cannot be effectively solved due to the absence of sufficiently informative or representative features required to build a meaningful predictive model.

Based on the insights and limitations observed during the analysis and modeling process, the following recommendations are proposed:

- **Improve Feature Collection**: Incorporate more informative variables such as real-time equipment usage logs, machine types, maintenance schedules, and operator behavior. These may provide stronger signals for predicting energy consumption.
- **Sensor Placement Review**: Re-evaluate the relevance and granularity of zone-based measurements. Adding sensor data specific to equipment zones rather than general zones may help.
- **Integrate Operational Data**: Include production volume, shift timings, and workload information, which directly influence equipment usage and energy draw.
- **Regular Monitoring**: Establish real-time monitoring dashboards for energy metrics, allowing timely interventions.






