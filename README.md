# NYC Taxi Fare Estimation Project

New York City TLC is an agency responsible for licensing and regulating New York City's taxi cabs and for-hire vehicles. The agency has partnered with us to develop a regression model that helps estimate taxi fares before the ride, based on data that TLC has gathered. 

The TLC data comes from over 200,000 taxi and limousine licensees, making approximately one million combined trips per day. 

**Note**: This project's dataset was created for pedagogical purposes and may not be indicative of New York City taxi cab riders' behavior.

## Project Structure

This project is divided into several steps, each documented in separate Jupyter notebooks. Here is a breakdown of the project structure:

1. **Data Cleaning**
    - Before any analysis, data cleaning is a crucial step to ensure the quality of the data. This step involves handling missing values, outlier detection, and data type conversions.
    - [Data Cleaning Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/1-Data%20cleaning_Taxi%20Fare%20Estimation.ipynb)

2. **Feature Engineering**
    - Feature engineering involves creating new features from the raw data that can help improve the performance of the machine learning model. This project explores two different methods of feature engineering.
    - Method 1: [Feature Engineering Method 1 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/2-Feature%20Engineering_Taxi%20Fare%20Estimation_MLR.ipynb)
    - Method 2: [Feature Engineering Method 2 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/2-Feature%20Engineering_Taxi%20Fare%20Estimation_MLR2.ipynb)

3. **Modeling**
    - After feature engineering, the next step is to build and train the machine learning models. This project explores two different modeling approaches.
    - Modeling Method 1: [Modeling Method 1 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/3-MLR_Taxi%20Fare%20Estimation.ipynb)
    - Modeling Method 2: [Modeling Method 2 Notebook](https://github.com/Yorgho/TaxiFareEstimationModel/blob/main/3-MLR_Taxi%20Fare%20Estimation2.ipynb)

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
