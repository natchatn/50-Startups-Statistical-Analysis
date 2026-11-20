# 50 Startups: Statistical Analysis & Regression Modeling

A Python data analysis project exploring the relationship between business expenditures and startup profitability through exploratory data analysis (EDA), statistical visualization, hypothesis testing, and linear regression.

Developed for **DES432 – Statistics and Data Modeling** at Sirindhorn International Institute of Technology (SIIT), Thammasat University.

## Project Overview

This project analyzes financial data from 50 startups across three U.S. states to investigate how R&D, administration, and marketing expenditures relate to company profits.

The goal is to identify meaningful patterns, compare statistical models, and better understand the relationships between business spending and profitability.

## Dataset

**Source:** [50 Startups Dataset – Kaggle (farhanmd29)](https://www.kaggle.com/datasets/farhanmd29/50-startups)

The dataset contains **50 observations and 5 variables**.

| Variable | Description |
|---|---|
| R&D Spend | Research and development expenses |
| Administration | Administrative expenses |
| Marketing Spend | Marketing expenses |
| State | Startup location (New York, California, or Florida) |
| Profit | Company profit (target variable) |

The dataset is publicly accessible on Kaggle. Credit goes to the dataset publisher, `farhanmd29`.

## Tools & Technologies

- **Python** – Data analysis and statistical modeling
- **Pandas** – Data manipulation and descriptive statistics
- **Matplotlib & Seaborn** – Data visualization
- **Statsmodels** – OLS regression and hypothesis testing
- **SciPy** – Statistical diagnostic plots
- **Scikit-learn** – Data scaling exploration
- **Jupyter Notebook / Google Colab** – Development environment

## Methodology

### 1. Data Preparation

- Loaded and inspected the dataset using Pandas.
- Checked for missing values and duplicate records.
- Examined potential outliers using box plots and scatter plots.
- Converted the categorical `State` variable into dummy variables.
- Explored feature scaling using `StandardScaler`.

No missing values or duplicate records were found. The final regression models used the original spending variables without scaling or State predictors.

### 2. Exploratory Data Analysis (EDA)

Created visualizations to examine financial patterns and relationships:

- Histograms showing the distributions of business expenditures and profit
- Scatter plots comparing each spending category with profit
- Correlation heatmap showing relationships between numerical variables
- Summary statistics describing the financial data

### 3. Hypothesis Testing

Used Ordinary Least Squares (OLS) regression to test the relationship between R&D spending and profit.

- **H₀:** The R&D spending coefficient equals zero.
- **H₁:** The R&D spending coefficient does not equal zero.

The analysis found a statistically significant positive relationship between R&D spending and profit (p < 0.05).

### 4. Regression Modeling

Built and compared two regression models:

**Simple Linear Regression (SLR)**

- Uses R&D spending to explain profit.

**Multiple Linear Regression (MLR)**

- Uses R&D, marketing, and administration spending to explain profit.

Both models were evaluated using R² and Adjusted R². Residual and Q-Q plots were also used to examine regression assumptions.

## Results & Key Findings

### Model Comparison

| Model | R² | Adjusted R² |
|---|---:|---:|
| Simple Linear Regression | 0.9465 | 0.9454 |
| Multiple Linear Regression | 0.9507 | 0.9475 |

*These are in-sample results calculated using the same 50 observations used to fit the models.*

### Key Findings

- **R&D spending** showed the strongest positive correlation with profit (r ≈ 0.97).
- **Marketing spending** had a positive correlation with profit (r ≈ 0.75), but was not statistically significant in the multiple regression model.
- **Administration spending** showed a weak correlation with profit (r ≈ 0.20).
- The multiple regression model achieved a slightly higher R², but additional predictors provided only a small improvement.

Overall, R&D spending was the strongest statistical predictor of profitability within this dataset.

## How to Run

**1. Clone the repository**

```bash
git clone https://github.com/natchatn/50-Startups-Statistical-Analysis.git
cd 50-Startups-Statistical-Analysis
```

**2. Install dependencies**

```bash
pip install pandas matplotlib seaborn scipy scikit-learn statsmodels notebook
```

**3. Download the dataset**

Download the CSV file from [50 Startups on Kaggle](https://www.kaggle.com/datasets/farhanmd29/50-startups).

Place `50_Startups.csv` in the same directory as the notebook.

**4. Run the notebook**

```bash
jupyter notebook Project2_50startups.ipynb
```

Run the cells sequentially to reproduce the analysis, visualizations, and regression results.

## Project Structure

```text
50-Startups-Statistical-Analysis/
├── Project2_50startups.ipynb
├── Statistic 50 start-up.pdf
└── README.md
```

The dataset must be downloaded separately from Kaggle and placed in the repository directory before running the notebook.

## Limitations

- The dataset contains only 50 observations, limiting generalization to other startups.
- The models were evaluated on training data without a separate test set.
- Important business factors, such as industry, company size, and funding, are not included.
- Correlation and regression results do not establish causal relationships.
