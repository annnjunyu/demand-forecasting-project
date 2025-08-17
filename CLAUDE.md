# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a data science internship training project focused on demand forecasting. The project involves analyzing sales data to predict product demand using machine learning techniques. The main dataset contains information about product sales including prices, promotions, and units sold.

## Repository Structure

```
Project/
├── archive/
│   ├── train_0irEZ2H.csv           # Training data (150,150 records)
│   ├── test_nfaJ3J5.csv            # Test data (13,860 records)
│   └── sample_submission_pzljTaX.csv # Sample submission template
├── CLAUDE.md                       # This file
└── readme.txt                      # Project description in Chinese
```

## Data Description

The dataset contains the following columns:
- `record_ID`: Unique identifier for each record
- `week`: Date of the sales record (format: yy/mm/dd)
- `store_id`: Store identifier
- `sku_id`: Product identifier
- `total_price`: Actual selling price
- `base_price`: Regular price without discounts
- `is_featured_sku`: Whether the product was featured (1/0)
- `is_display_sku`: Whether the product was displayed prominently (1/0)
- `units_sold`: Target variable - number of units sold (only in training data)

## Key Data Files

1. **train_0irEZ2H.csv**: Training dataset with 150,150 records containing all columns including the target variable `units_sold`
2. **test_nfaJ3J5.csv**: Test dataset with 13,860 records missing the `units_sold` column
3. **sample_submission_pzljTaX.csv**: Template for submission format

## Commands for Development

### Data Exploration
```bash
# Check data files
ls -la archive/
```

### Python Environment
```bash
# Install required packages
pip install pandas numpy matplotlib seaborn scikit-learn

# For advanced ML models
pip install xgboost lightgbm
```

### Jupyter Notebook Development
```bash
# Start Jupyter notebook for interactive analysis
jupyter notebook

# Or start Jupyter lab
jupyter lab
```

## Code Architecture

The project follows a typical data science workflow:

1. **Data Ingestion Layer**: Raw CSV files in the `archive/` directory
2. **Exploration Layer**: (To be implemented) Python scripts or Jupyter notebooks for data analysis
3. **Preprocessing Layer**: (To be implemented) Feature engineering and data cleaning
4. **Modeling Layer**: (To be implemented) Machine learning models for demand forecasting
5. **Output Layer**: Submission files in the required Kaggle format

Note: The preprocessing and modeling layers are not yet implemented in the current repository. These will need to be created as part of the internship project.

## Data Processing Workflow

1. Load training and test data from CSV files
2. Handle missing values (particularly one missing value in `total_price`)
3. Convert `week` column to datetime and extract features
4. Detect and handle outliers in `units_sold`
5. Engineer new features:
   - Price discount and discount ratio
   - Promotion flag combining featured and display status
   - Log transformations of price features
6. Optimize data types for memory efficiency

## Key Insights from Current Analysis

- Training data has 150,150 records, test data has 13,860 records
- One missing value in `total_price` column of training data
- Data spans multiple stores and SKUs over time
- Promotion features (`is_featured_sku`, `is_display_sku`) likely important for demand prediction
- Significant variation in `units_sold` (1 to 2,876 units)

## Recommended Implementation Approach

### Phase 1: Data Exploration and Analysis
- Create Jupyter notebooks for exploratory data analysis
- Analyze distributions, correlations, and patterns in the data
- Visualize sales trends over time, by store, and by product

### Phase 2: Feature Engineering
- Implement date feature extraction (day of week, month, etc.)
- Calculate price discount features (difference and ratio between base_price and total_price)
- Create promotion indicators
- Apply log transformations where appropriate

### Phase 3: Model Development
- Start with baseline models (Linear Regression, Random Forest)
- Progress to advanced models (XGBoost, LightGBM)
- Implement cross-validation for robust evaluation
- Tune hyperparameters for optimal performance

### Phase 4: Evaluation and Submission
- Evaluate model performance using appropriate metrics (RMSE, MAE)
- Generate predictions on test set
- Format submissions according to sample_submission_pzljTaX.csv
- Document results and insights

## Expected Deliverables

1. Jupyter notebooks for data exploration and modeling
2. Python scripts for preprocessing and feature engineering
3. Trained machine learning models
4. Prediction files in submission format
5. Documentation of approach and findings