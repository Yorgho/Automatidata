# NYC Taxi Fare Estimation Project

New York City TLC is an agency responsible for licensing and regulating New York City's taxi cabs and for-hire vehicles. The agency has partnered with us to develop a regression model that helps estimate taxi fares before the ride, based on data that TLC has gathered. 

The TLC data comes from over 200,000 taxi and limousine licensees, making approximately one million combined trips per day. 

**Note**: This project's dataset was created for pedagogical purposes and may not be indicative of New York City taxi cab riders' behavior.

## Data Dictionary

The following image provides a data dictionary for the project:

![Data Dictionary](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/Data_Dictionary.png)

## Project Structure

This project is divided into several steps, each documented in separate Jupyter notebooks. Here is a breakdown of the project structure:

1. **Data Cleaning**
    - Before any analysis, data cleaning is a crucial step to ensure the quality of the data. This step involves handling missing values, outlier detection, and data type conversions.
    - [Data Cleaning Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/1-Data%20cleaning_Taxi%20Fare%20Estimation.ipynb)
      
      This script conducts an exploratory data analysis (EDA) on a New York City taxi fare dataset to identify and address data quality issues before building a regression model for fare prediction.
      Initial inspection reveals potential issues such as zero trip distances, outliers in fare amounts, and negative fare values.
      The script converts datetime columns to the correct format and sorts the data to identify anomalies, finding that the most expensive rides aren't always the longest.
      Further analysis of RatecodeID shows several trips with zero distance but non-zero fares, often associated with specific rate codes like negotiated or fixed rates.
      This indicates the need for further data cleaning, particularly filtering out trips with zero distances linked to certain RatecodeID values.
      Overall, the script highlights key areas for data preprocessing to ensure the reliability of the subsequent regression model.

2. **Feature Engineering**
    - Feature engineering involves creating new features from the raw data that can help improve the performance of the machine learning model. This project explores two different methods of feature engineering.
    - `Method 1`: [Feature Engineering Method 1 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/2-Feature%20Engineering_Taxi%20Fare%20Estimation_MLR.ipynb)  

      We transformed the 2017 Yellow Taxi Trip dataset by converting datetime columns, calculating trip durations, and identifying outliers. We added mean distance and duration features based on historical trip data and flagged rush hour trips for temporal context.            Unnecessary columns were dropped to streamline the dataset. These steps were performed to prepare the data specifically for training a linear regression model, enhancing its predictive accuracy for taxi fares.
      
    - `Method 2`: [Feature Engineering Method 2 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/2-Feature%20Engineering_Taxi%20Fare%20Estimation_MLR2.ipynb)
      
      Method 2 employs a similar approach to Method 1 but does not calculate any means, instead opting to analyze each trip individually.
      This approach enhances technical accuracy by avoiding the calculation of mean distance and mean duration, which in Method 1 introduced potential bias by contaminating the training data with information from the test data.
      Consequently, Method 2 mitigates this issue, leading to a more robust and unbiased model.
      
3. **Modeling**
    - After feature engineering, the next step is to build and train the machine learning models. This project explores two different modeling approaches.
    - `Modeling Method 1`: [Modeling Method 1 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/3-MLR_Taxi%20Fare%20Estimation.ipynb)
  
      This script performs a comprehensive multiple linear regression analysis to predict taxi fares based on trip data obtained using [`method 1`](#method-1) earlier, focusing on key assumptions and metrics for model validation. It starts with data preprocessing,
      including splitting the dataset into training and testing sets, and standardizing the features. A correlation matrix and heatmap are used to identify multicollinearity,
      followed by calculating the variance inflation factor (VIF) to ensure no two predictors are highly correlated.
      The regression model is then fitted to the training data and evaluated using R², MAE, MSE, and RMSE metrics, achieving a high R² score, indicating good model performance.
      Diagnostic plots, such as residuals distribution and scatter plots, are created to check the assumptions of normality and homoscedasticity.
      
    - `Modeling Method 2`: [Modeling Method 2 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/3-MLR_Taxi%20Fare%20Estimation2.ipynb)

      The multiple linear regression model developed using [`method 2`](#method-2) data demonstrates a high level of accuracy, as evidenced by the R² values for both the training (0.9737) and testing (0.9835) datasets.
      The model's evaluation metrics, such as MAE, MSE, and RMSE, further affirm its reliability and precision in predicting fares.
      The VIF values indicate that multicollinearity among the predictors is not excessively high, although trip_distance and duration do exhibit some correlation. Despite this, including both variables improves the model's predictive power.
      The assumptions of normality and homoscedasticity of residuals were validated through visualization, indicating that the errors are normally distributed and exhibit constant variance across the model.
      The standardized coefficients provide an interpretable understanding of the model: for every 1-mile increase in trip distance, the fare is expected to increase by approximately $1.96, highlighting the direct relationship between distance and fare.
      Overall, this model serves as a robust predictor of taxi fares, suitable for further integration into more complex machine learning models.

### Getting Started

To get started with this project, follow these steps:

1. **Clone the Repository**: Run the following command to create a local copy of the repository:

    ```sh
    git clone https://github.com/Yorgho/TaxiFareEstimationModel.git
    ```

2. **Navigate to the Project Directory**: Change to the project directory with:

    ```sh
    cd TaxiFareEstimationModel
    ```

3. **Install Required Packages**: Install the necessary Python packages by running:

    ```sh
    pip install -r requirements.txt
    ```

These steps will set up your local environment so you can start exploring and working with the project’s Jupyter notebooks and other files.
