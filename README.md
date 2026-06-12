# Data Ingestion and Cleaning Pipeline

## Overview
This project demonstrates a standard data ingestion and cleaning pipeline using Python and pandas. The core objective of the project is to load raw, untidy data, perform Exploratory Data Analysis (EDA), handle missing values and inconsistencies, and export a clean, normalized dataset ready for downstream analysis or machine learning tasks.

## Project Structure
```text
.
├── data/
│   ├── budgetwise_synthetic_dirty.csv  # Raw dataset downloaded from Kaggle
│   └── Clean_budgetwise_data.csv       # Processed and cleaned dataset (Output)
├── notebook/
│   └── main.ipynb                      # Jupyter notebook containing ingestion and cleaning logic
├── .gitignore                          # Ignores environment files and unnecessary artifacts
└── README.md                           # Project documentation (this file)

```

## Dataset Information

The raw dataset used in this project was sourced from Kaggle. It contains synthetic transaction data (`budgetwise_synthetic_dirty.csv`) mimicking a budget-tracking application.

**Key Features Include:**

* `transaction_id`, `user_id`: Identifiers for the transaction and user.
* `date`: The date the transaction occurred (initially in mixed formats).
* `transaction_type`, `category`: Classification of the financial activity.
* `amount`: Financial value of the transaction.
* `payment_mode`, `location`, `notes`: Additional metadata.

## Key Processing Steps

The `main.ipynb` notebook systematically walks through the following pipeline:

1. **Data Ingestion:** Loads the raw `.csv` data from the `data/` directory using `pandas`.
2. **Exploratory Data Analysis (EDA):**
* Inspects the initial structure using `df.head()` and `df.shape`.
* Analyzes unique values using `df.value_counts()`.
* Identifies null/missing values using `df.isnull().sum()`.
* Generates summary statistics using `df.describe()`.


3. **Data Cleaning & Normalization:**
* Normalizes data types (e.g., parsing mixed-format strings into standard `datetime` objects and coercing strings to numeric floats).
* Handles missing values by appropriately dropping or imputing `NaN` rows.
* Identifies and removes duplicate records.
* Cleans category strings by stripping whitespace, capitalizing, and mapping misspelled categories to correct ones.


4. **Data Export:** Saves the final, thoroughly cleaned Pandas DataFrame into a new CSV file (`Clean_budgetwise_data.csv`) within the `data/` folder.

## Getting Started

### Prerequisites

To run this notebook, you will need Python 3 installed along with the following libraries:

* `pandas`
* `matplotlib`
* `jupyter`

You can install the dependencies using pip:

```bash
pip install pandas matplotlib jupyter

```

### Usage

1. Clone this repository to your local machine.
2. Ensure your raw Kaggle dataset is placed inside the `data/` folder and named appropriately.
3. Launch Jupyter Notebook from your terminal.
4. Navigate to the `notebook/` folder and open `main.ipynb`.
5. Run the cells sequentially to ingest the data, view the exploratory analysis, and generate the cleaned CSV.

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page if you want to contribute.

## License

This project is open-source and available under the MIT License.

