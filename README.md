# customer-potential-prediction
Traditional banking models often focus on a customer’s current assets, which leads to overlooking high-growth segments. This project aims to transform banking marketing from a reactive stance into a proactive framework by analyzing a dataset of 100,000 customers to identify those with high future financial volume (High-Potential).

Technical Implementation & Workflow
This project is structured as an end-to-end data science pipeline, moving from raw data to a production-ready deployment model.

1. Exploratory Data Analysis (EDA)
A comprehensive EDA process was conducted to understand the dataset's characteristics and define the modeling strategy:

Feature Selection: Variables with high cardinality or no predictive power, such as Musteri_ID and Plaka_Kodu, were dropped to reduce noise.

Correlation Analysis: Statistical relationships between demographic features and the target variable (Economic_Potential_Score) were analyzed to identify the most significant predictors.

2. Feature Engineering & Preprocessing
To enhance the model's generalization capabilities, the following Feature Engineering techniques were applied:

Numerical to Categorical Binning: The continuous Age variable was transformed using Binning into three distinct categories: 'Young', 'Professional', and 'Retired'. This allows the model to capture trends based on life-cycle stages rather than individual ages.

One-Hot Encoding: To process categorical features (Occupation, City Type, etc.) mathematically, One-Hot Encoding was implemented, transforming text labels into a numerical vector format suitable for machine learning algorithms.

3. Model Architecture: Random Forest Regressor
The Random Forest Regressor, an Ensemble Learning algorithm, was chosen for the predictive engine:

Handling Non-Linearity: Unlike linear models, the forest of decision trees effectively captures complex, non-linear interactions within banking and demographic data.

Hyperparameter Configuration: The model was configured with 100 trees (n_estimators=100) and a fixed random_state to ensure result reproducibility.

4. Performance Metrics & Evaluation
The model's performance was validated on a 20% "hold-out" test set, yielding the following results:

R² (Coefficient of Determination): %97.26 – The model successfully explains 97% of the variance in the target data.

Mean Squared Error (MSE): 0.0010 – Indicates an extremely low variance in prediction errors, showcasing high precision.

5. Model Interpretability (XAI)
To move beyond "black-box" modeling, Explainable AI (XAI) principles were applied:

Feature Importance: Using Plotly for interactive visualization, the "Feature Importance" was mapped to show exactly which variables (e.g., City Type or Occupation) drive the final potential score.

6. Model Serialization & Deployment Readiness
The final model is fully "production-ready":

Joblib Serialization: The trained model was serialized into a .pkl file format using the Joblib library.

Real-time Inference: This setup allows for real-time inference, enabling the system to generate instant potential scores for new customers without the need for retraining.
