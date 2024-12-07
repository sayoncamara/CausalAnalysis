# Causal Analysis of Rental Price Determinants: Policy Insights for Real Estate Interventions in Brussels

Introduction

In today's dynamic real estate market, understanding the factors that influence rental prices is critical for property owners, investors, and policymakers. Traditional models often provide predictions based on correlations, but they may not fully capture the causal relationships between different property features and rental prices. This project takes a step further by employing causal inference techniques to determine not only which features are most important in predicting rental prices but also how interventions like adding amenities or making structural improvements can impact rental returns.

The project begins with  exploratory data analysis (EDA), as the dataset used is notably dirty, with a significant portion of missing values. Careful imputation techniques were employed to handle these gaps and prepare the data for analysis. After cleaning the data, a monthly rental price prediction model was built to extract the most important predictive features using SHAP values, which helped highlight the top-ranking variables that contribute to rental price predictions.

However, while SHAP values reveal feature importance in a predictive sense, they do not provide insights into the causal effects of these features. To bridge this gap, we leverage CausalAnalysis from EconML to determine which features not only correlate with higher rents but also causally impact rental prices. By understanding the actual causal relationships, we can provide more reliable insights into how specific property features influence rental income.

In the next phase, we explore how property features—such as heating systems, solar panels, furnishing, and building conditions—affect rental prices through causal inference models. Using tools like policy trees and heterogeneity analysis, we dive deep into how these features impact different types of properties.

Ultimately, this project aims to offer actionable insights for real estate decision-makers, highlighting which property features have the greatest potential to increase rental prices and guiding cost-effective property improvements.

## Dataset Features

| Feature Name | Description |
|-------------|-------------|
| Monthly rental price | Monthly cost charged for renting the property in Brussels |
| Living area | Total habitable area of the property in square meters |
| Bedrooms | Number of rooms designated as bedrooms in the property |
| Energy class | Energy performance rating of the property (e.g., A, B, C, D, E, F, G) |
| Building condition | Overall state of the property (e.g., excellent, good, to renovate) |
| Location | Area/neighborhood within Brussels where property is located |
| Construction year | Year when the building was originally constructed |
| Heating type | Primary heating system used (e.g., central, electric, gas) |
| Double glazing | Whether windows have double-pane insulation for energy efficiency |
| Furnished | Whether the property is rented with furniture included |


## Model Interpretation: Feature Importance Analysis

![SHAP Values Impact on Rental Price Prediction](./Shapley.png)

Our model's predictions were analyzed using SHAP (SHapley Additive exPlanations) values to understand the impact of each feature on rental price predictions. The analysis reveals:

### Key Insights:
- **Total Space** has the strongest impact on rental prices, showing significant influence on model predictions
- **Toilets**, **Terrace surface**, and **Furnished** status are the next most influential features
- **Building Characteristics** (Bathrooms, Bedrooms, Kitchen surface) show moderate impact
- **Construction year** and **Floor** level demonstrate notable influence
- Specific location indicators (e.g., **zip_code_1081**) have measurable effects on price predictions
- Basic amenities and features like **Kitchen type** and **Bedroom surface areas** show relatively lower but consistent impact

The color gradient in the plot indicates feature values (blue = low, red = high), while the horizontal position shows the magnitude of impact on the model's rental price predictions.
