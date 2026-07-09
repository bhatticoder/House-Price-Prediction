# House Price Prediction

An end-to-end machine learning project that predicts house prices using the King County (WA) house sales dataset. The notebook demonstrates data loading, exploratory data analysis (EDA), feature engineering, model training, and model evaluation.

## Project overview
Predicting house prices is a common supervised regression task. This project compares multiple approaches (Linear Regression, Polynomial Regression, and LightGBM) and evaluates them with metrics such as $R^2$ and Mean Absolute Error (MAE).

## Dataset
The dataset contains historical house sale records from King County, Washington (including Seattle) between May 2014 and May 2015 (≈21k rows, ~21 features).

### Key features
| Feature | Description |
|---|---|
| `id` | Unique identifier for the sale |
| `date` | Date the house was sold |
| `price` | Target variable — sale price |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `sqft_living` | Interior living area (square feet) |
| `sqft_lot` | Lot size (square feet) |
| `floors` | Number of floors |
| `waterfront` | 1 if waterfront view, else 0 |
| `view` | View score (0–4) |
| `condition` | Condition score (1–5) |
| `grade` | Construction/quality grade (1–13) |
| `sqft_above` | Sqft above ground |
| `sqft_basement` | Sqft of basement |
| `yr_built` | Year built |
| `yr_renovated` | Year renovated (0 if none) |
| `zipcode` | ZIP code |
| `lat`, `long` | Geographic coordinates |

## Tech stack & libraries
- Python 3
- Data: `pandas`, `numpy`
- Visualization: `matplotlib`, `seaborn`
- Machine learning: `scikit-learn`, `lightgbm`

## Project workflow
1. Setup & data loading — import libraries and inspect the dataset with `.head()`, `.info()`, and `.describe()`.
2. Exploratory data analysis (EDA) — visualize distributions and correlations, identify important predictors.
3. Preprocessing & feature engineering — handle missing values, drop identifiers (e.g., `id`, `date`), create/transform features, scale where appropriate, and split data (80/20).
4. Model training & tuning — train Linear Regression, Polynomial Regression, and LightGBM; tune hyperparameters when useful.
5. Evaluation — compare models using $R^2$, MSE, and MAE and select the best-performing model.

## Key insights
- `sqft_living` (living area) is one of the strongest positive predictors of price.
- `grade` and `sqft_above` also correlate positively with price.
- Geographic features (`lat`, `long`, `view`) show local pricing effects.

## How to run
1. Create a virtual environment and install dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install pandas numpy matplotlib seaborn scikit-learn lightgbm
```

2. Open the notebook `[Hourse_prediction.ipynb](Hourse_prediction.ipynb)` and run the cells. The notebook contains the full EDA, preprocessing, model training, and evaluation steps.

## Next steps (optional)
- Add a `requirements.txt` or `environment.yml` for reproducible installs.
- Add model serialization (e.g., `joblib`) and a small inference script to predict new samples.

---
Updated and formatted README for clarity and quick usage.
