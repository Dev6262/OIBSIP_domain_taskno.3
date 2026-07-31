Car Price Prediction with Machine Learning
A regression project that predicts the selling price of used cars based on features like brand, age, mileage, fuel type, and transmission. Built with Python, Pandas, Scikit-learn, Matplotlib, and Seaborn in a Jupyter Notebook.

Project Objectives
Clean and standardize a real-world used-car dataset.
Engineer useful features (car age, brand) from raw columns.
Explore how price relates to fuel type, age, and other factors.
Train and compare multiple regression models.
Identify which features most strongly drive used car prices.
Dataset
Source: "Vehicle dataset from CarDekho" on Kaggle — https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho

Description: [BRIEF_PROJECT_DESCRIPTION — e.g., "Used car listings from CarDekho, including car name, year, selling price, kilometers driven, fuel type, seller type, and transmission."]

Typical columns (naming can vary slightly by dataset version):

Column	Description
name / Car_Name	Full car model name (used to extract brand)
year	Manufacturing year (used to calculate car age)
selling_price / Selling_Price	Target variable — the price the car sold for
present_price	Original showroom price (if available)
km_driven / Kms_Driven	Total kilometers driven
fuel / Fuel_Type	Petrol, Diesel, CNG, Electric, etc.
seller_type	Individual or Dealer
transmission	Manual or Automatic
owner	Number of previous owners
Requirements
Python 3.8+
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
Install dependencies:

pip install pandas numpy scikit-learn matplotlib seaborn jupyter
Getting the Data
Go to the CarDekho Vehicle Dataset page on Kaggle.
Download and unzip the CSV file.
Place it in a data/ folder in this project (or update DATASET_PATH in the notebook).
If your column names differ from the table above, adjust the COLUMN_MAP in the notebook's data-loading cell to match.
Project Structure
.
├── Car_Price_Prediction.ipynb   # Main analysis and modeling notebook
├── data/                        # Place the downloaded CSV here (not uploaded to GitHub)
└── README.md
Methodology
Data Cleaning — remove duplicates, handle missing values, and standardize inconsistent categorical text (e.g., "Petrol" vs "petrol") via consistent casing/whitespace handling.
Feature Engineering — calculate car_age from the year column, and extract brand from the car name column.
EDA — visualize the selling price distribution, compare price across fuel types with box plots, and examine price vs. car age with a scatter plot.
Encoding — one-hot encode categorical features (brand, fuel, seller type, transmission, owner) inside a ColumnTransformer, so encoding is applied consistently and without leakage between train and test sets.
Correlation Analysis — heatmap of numeric features against selling price.
Model Training — train and compare three regression models: Linear Regression, Random Forest Regressor, and Gradient Boosting Regressor.
Evaluation — compare models using MAE, RMSE, and R² score.
Feature Importance — plot the top features driving predictions for the best-performing model.
Each step in the notebook includes a written observation explaining the insight behind the visualization or result.

Key Findings
(To be completed after running the notebook on the actual dataset — a summary of the best model, its performance, and the top price-driving features belongs here once the analysis has been executed.)

How to Run
Clone or download this project.
Install the required libraries (see Requirements above).
Add the dataset CSV to the data/ folder (see Getting the Data).
Launch Jupyter:
jupyter notebook
Open Car_Price_Prediction.ipynb and run all cells in order.
