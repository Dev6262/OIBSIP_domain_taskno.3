# Car Price Prediction with Machine Learning

A regression project that predicts the selling price of used cars based on features like brand,
age, mileage, fuel type, and transmission. Built with Python, Pandas, Scikit-learn, Matplotlib,
and Seaborn in a Jupyter Notebook.

## Project Objectives

- Clean and standardize a real-world used-car dataset.
- Engineer useful features (car age, brand) from raw columns.
- Explore how price relates to fuel type, age, and other factors.
- Train and compare multiple regression models.
- Identify which features most strongly drive used car prices.

## Dataset

- **Source:** "Vehicle dataset from CarDekho" on Kaggle — [https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho)
- **Description:** [BRIEF_PROJECT_DESCRIPTION — e.g., "Used car listings from CarDekho, including car name, year, selling price, kilometers driven, fuel type, seller type, and transmission."]
- **Typical columns** (naming can vary slightly by dataset version):

  | Column | Description |
  |---|---|
  | `name` / `Car_Name` | Full car model name (used to extract brand) |
  | `year` | Manufacturing year (used to calculate car age) |
  | `selling_price` / `Selling_Price` | Target variable — the price the car sold for |
  | `present_price` | Original showroom price (if available) |
  | `km_driven` / `Kms_Driven` | Total kilometers driven |
  | `fuel` / `Fuel_Type` | Petrol, Diesel, CNG, Electric, etc. |
  | `seller_type` | Individual or Dealer |
  | `transmission` | Manual or Automatic |
  | `owner` | Number of previous owners |

## Requirements

- Python 3.8+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- jupyter

Install dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

## Getting the Data

1. Go to the [CarDekho Vehicle Dataset page](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho) on Kaggle.
2. Download and unzip the CSV file.
3. Place it in a `data/` folder in this project (or update `DATASET_PATH` in the notebook).
4. If your column names differ from the table above, adjust the `COLUMN_MAP` in the notebook's
   data-loading cell to match.

## Project Structure

```
.
├── Car_Price_Prediction.ipynb   # Main analysis and modeling notebook
├── data/                        # Place the downloaded CSV here (not uploaded to GitHub)
└── README.md
```

## Methodology

1. **Data Cleaning** — remove duplicates, handle missing values, and standardize inconsistent
   categorical text (e.g., `"Petrol"` vs `"petrol"`) via consistent casing/whitespace handling.
2. **Feature Engineering** — calculate `car_age` from the `year` column, and extract `brand` from
   the car name column.
3. **EDA** — visualize the selling price distribution, compare price across fuel types with box
   plots, and examine price vs. car age with a scatter plot.
4. **Encoding** — one-hot encode categorical features (brand, fuel, seller type, transmission,
   owner) inside a `ColumnTransformer`, so encoding is applied consistently and without leakage
   between train and test sets.
5. **Correlation Analysis** — heatmap of numeric features against selling price.
6. **Model Training** — train and compare three regression models: Linear Regression, Random
   Forest Regressor, and Gradient Boosting Regressor.
7. **Evaluation** — compare models using MAE, RMSE, and R² score.
8. **Feature Importance** — plot the top features driving predictions for the best-performing
   model.

Each step in the notebook includes a written observation explaining the insight behind the
visualization or result.

## Key Findings

*(To be completed after running the notebook on the actual dataset — a summary of the best model,
its performance, and the top price-driving features belongs here once the analysis has been
executed.)*

## How to Run

1. Clone or download this project.
2. Install the required libraries (see **Requirements** above).
3. Add the dataset CSV to the `data/` folder (see **Getting the Data**).
4. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
5. Open `Car_Price_Prediction.ipynb` and run all cells in order.

---

## Deploying This Project to GitHub — Super Simple Guide 🌟

Think of GitHub like a big toy box in the sky where your project lives safely and others can see
it. We'll put these things in the box:

- `Car_Price_Prediction.ipynb` (your notebook)
- `README.md` (this file — the note explaining your project)

### Step 1: Make a GitHub Account (Get Your Toy Box)

1. Open your web browser and go to **github.com**
2. Click **"Sign up"**.
3. Type in your **email address**.
4. Make up a **password** — your secret key, so pick something safe.
5. Choose a **username** — the nickname everyone will see.
6. Follow the on-screen steps (a quick check that you're not a robot 🤖).
7. Check your email inbox for a message from GitHub and click the confirmation link.

🎉 You now have your own toy box!

### Step 2: Make a New Box for This Project (a "Repository")

1. Once logged in, click the **"+"** icon near the top of the page.
2. Click **"New repository"**.
3. Type a name, e.g. `car-price-prediction` in **"Repository name"**.
4. (Optional) Add a short description, like: *"Predicting used car selling prices with regression models."*
5. Choose:
   - **Public** = anyone can see your project (open toy box).
   - **Private** = only you can see it (locked toy box).
6. Check **"Add a README file"**.
7. Click the green **"Create repository"** button.

🎉 You now have a special box just for this project!

### Step 3: Put Your Files Into the Box

1. On your repository's page, click **"Add file" → "Upload files"**.
2. Find your project folder on your computer and **drag** these files onto the GitHub page:
   - `Car_Price_Prediction.ipynb`
   - `README.md`
3. Scroll down to **"Commit changes"** — this means *"Yes, save this in my box now."*
4. Click the green **"Commit changes"** button.

🎉 Your project is now living on GitHub!

> 💡 **About your data folder:** It's best not to upload the raw dataset CSV, since large files
> and license terms are best handled by pointing people to download it directly from Kaggle (your
> README above already explains how). If you want GitHub to always skip certain files/folders
> automatically, add a `.gitignore` file containing:
> ```
> data/
> .ipynb_checkpoints/
> ```

### Step 4: Double-Check Your README

1. Click on **README.md** in your repository.
2. Click the pencil icon ✏️ to edit it.
3. Paste in the contents of this file if it isn't already there, filling in any placeholders
   (`[PROJECT_NAME]`, `[BRIEF_PROJECT_DESCRIPTION]`).
4. Click **"Commit changes"** to save.

🎉 All done!

### Quick Recap

| What you did | Toy-box version |
|---|---|
| Made a GitHub account | Got your own toy box |
| Made a repository | Made a special box for this project |
| Uploaded your notebook and README | Put your toys and instruction card inside |
| Saved with "Commit changes" | Closed the lid so it's safe |

## Notes

- Never commit real Kaggle credentials or API keys to a public repository.
- If the dataset's exact column names differ from what's assumed in the notebook, update the
  `COLUMN_MAP` and feature lists in the notebook accordingly.
