# Renewable-Energy-Forecasting-For-CleanEnergy-Innovations-Inc.

**Renewable Energy Forecasting: Wind Turbine Power Prediction (with-pandas-and-Machine-Learning)**

## Overview
This project focuses on analyzing and forecasting power generation from wind turbines using data science and machine learning techniques. The goal is to predict the **system power generated** by a wind turbine based on various environmental factors such as wind speed, wind direction, pressure, and air temperature.

By using exploratory data analysis (EDA) and machine learning models, we can gain insights into which features most impact energy production and build predictive models to help optimize power generation.

## Table of Contents
- [Data Description](#data-description)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Key Insights](#key-insights)
  - [Visualizations](#visualizations)
- [Machine Learning Models](#machine-learning-models)
  - [Model Selection](#model-selection)
  - [Hyperparameter Tuning](#hyperparameter-tuning)
  - [Performance Metrics](#performance-metrics)
- [Model Deployment](#model-deployment)
  - [Inference Script](#inference-script)
- [Recommendations](#recommendations)
- [How to Use This Repository](#how-to-use-this-repository)
- [Contributors](#contributors)
- [License](#license)

## Data Description
The dataset contains crucial features for the analysis and forecasting of wind turbine performance:

- **Time Stamp**: A timestamp indicating when each data point was recorded.
- **System Power Generated (kW)**: The amount of power generated by the turbine, measured in kilowatts (kW).
- **Wind Speed (m/s)**: Wind speed at the turbine location.
- **Wind Direction (degrees)**: Direction of the wind, measured in degrees.
- **Pressure (atm)**: Atmospheric pressure at the turbine location.
- **Air Temperature**: Temperature at the turbine location.

## Exploratory Data Analysis (EDA)

### Key Insights:
- **Wind Speed as the Dominant Factor**: Wind speed showed the strongest correlation with power generated. Higher wind speeds lead to higher power generation.
- **Wind Direction's Influence**: While wind direction affects turbine performance, its impact is smaller compared to wind speed.
- **Pressure and Air Temperature**: These features showed weaker correlations but still contribute to overall turbine efficiency.

### Visualizations:

#### Correlation Matrix:
This heatmap highlights the relationships between the different variables. Wind speed has the highest correlation with power generated.

![Correlation Matrix](visuals/correlation_matrix.png)

#### Predicted vs Actual Power Generation:
Shows how well the model predicted power generation compared to actual data.

![Predicted vs Actual](visuals/predicted_vs_actual.png)

#### Residual Plot:
Residuals help assess the accuracy of the model's predictions. Ideally, residuals should be randomly scattered around zero.

![Residual Plot](visuals/residual_plot.png)

## Machine Learning Models

### Model Selection:
Several models were tested, including:
- **Random Forest Regressor**
- **Gradient Boosting Regressor**
- **Linear Regression**

After tuning hyperparameters, the **Random Forest Regressor** emerged as the best-performing model.

### Hyperparameter Tuning:
We used **GridSearchCV** for hyperparameter tuning. The best hyperparameters for the Random Forest model were:

- `n_estimators`: 300
- `max_depth`: 20
- `min_samples_split`: 5

### Performance Metrics:
- **Mean Squared Error (MSE)**: 12.53
- **Root Mean Squared Error (RMSE)**: 3.54
- **Mean Absolute Error (MAE)**: 2.67

## Model Deployment

An inference script was created to deploy the best model for predicting wind turbine power generation. This script accepts new data, preprocesses it (including scaling and handling missing values), and makes predictions using the saved model.

### Inference Script:


`python scripts/inference.py --input data/new_wind_data.csv`


## Recommendations

- **Optimize Wind Turbine Alignment**:  
  Ensure turbines are optimally aligned with prevailing wind directions to maximize energy capture.

- **Monitor and Adjust for Atmospheric Conditions**:  
  While wind speed is the primary factor, adjustments for air pressure and temperature could yield small but impactful improvements.

- **Reduce Downtime**:  
  Address zero-power generation instances, especially during high wind events, to significantly increase energy output.

- **Further Model Improvements**:  
  Additional features, such as humidity or turbulence, could improve prediction accuracy for the models.



## How to Use This Repository

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/RenewableEnergyForecasting.git
    ```

2. **Install the dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Jupyter Notebook for EDA and Model Training**:
    ```bash
    jupyter notebook notebooks/eda_and_modeling.ipynb
    ```

4. **Use the inference script for deployment**:
    ```bash
    python scripts/inference.py
    ```

---

## Contributors

- **Ibrahim Ismaila**  
  - [LinkedIn](https://www.linkedin.com/in/ibrahim-ismaila)  
  - [GitHub](https://github.com/ibrahim-ismaila)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Pushing the Repository to GitHub

After organizing the project files and creating the `README.md`, you can push the repository to GitHub with the following commands:

1. **Commit the changes**:
    ```bash
    git add .
    git commit -m "Initial commit with full project structure and README"
    ```

2. **Push the repository to GitHub**:
    ```bash
    git push origin main
    ```

---

## Explanation of Structure:

- **Overview**: Introduces the project and its objectives.
- **Data Description**: Provides details about the dataset features.
- **EDA**: Lists key insights and includes visualizations.
- **Machine Learning Models**: Describes the models used, hyperparameter tuning, and performance metrics.
- **Model Deployment**: Details how to use the inference script to make predictions.
- **Recommendations**: Provides suggestions for improving turbine performance.
- **How to Use This Repository**: Instructions on cloning and running the project.
- **Contributors and License**: Acknowledges contributors and licensing details.

This `README.md` serves as an informative and comprehensive guide for anyone visiting your repository, covering everything from data insights to model deployment and further steps for repository management.
