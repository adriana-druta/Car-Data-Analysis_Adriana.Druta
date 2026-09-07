# 🚗 Car Data Analysis (Python)

![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A end-to-end data analytics project that cleans, transforms, and explores a real-world **car specifications and pricing dataset** to uncover the trends behind horsepower, fuel efficiency, drivetrain, and market pricing.

---

## 📖 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset](#️-dataset)
- [Objectives](#-objectives)
- [Project Workflow](#️-project-workflow)
  - [1. Data Cleaning](#1-data-cleaning)
  - [2. Feature Engineering](#2-feature-engineering)
  - [3. Exploratory Data Analysis](#3-exploratory-data-analysis-eda)
- [Visualizations](#-visualizations)
- [Key Insights](#-key-insights)
- [Tech Stack](#-tech-stack)
- [Repository Structure](#-repository-structure)
- [How to Run](#-how-to-run)
- [Author](#-author)

---

## 🔎 Project Overview

This project uses Python to turn a raw, messy car dataset into a clean, analysis-ready one and then explores it to answer practical questions about the automotive market: how price relates to horsepower, how drivetrain affects cost, and how fuel efficiency shifts across transmission types. It covers the full mini data-analytics pipeline — cleaning, feature engineering, descriptive statistics, group comparisons, correlation analysis, and visualization.

---

## 🗂️ Dataset

The dataset contains specifications and pricing information for thousands of vehicles.

📥 **Source:** [Google Drive – car dataset (CSV)](https://drive.google.com/file/d/19V7VjHs4J8idTko7NQUT95ZJO2ZQSGWh/view?usp=sharing)

| Column | Description |
|---|---|
| `Make` | Manufacturer of the car (e.g., Toyota, Ford, BMW) |
| `Model` | Specific model name of the car |
| `Year` | Production year of the car |
| `Engine Fuel Type` | Type of fuel used (gas, diesel, electric, hybrid, …) |
| `Engine HP` | Horsepower of the engine |
| `Engine Cylinders` | Number of engine cylinders |
| `Transmission Type` | Automatic, manual, etc. |
| `Driven_Wheels` | Drivetrain (FWD, RWD, AWD) |
| `Number of Doors` | Number of doors (2, 4, …) |
| `Market Category` | Market segment (SUV, sedan, luxury, …) |
| `Vehicle Size` | Compact, mid-size, large |
| `Vehicle Style` | Coupe, convertible, hatchback, … |
| `highway MPG` | Estimated highway fuel economy |
| `city mpg` | Estimated city fuel economy |
| `Popularity` | Numerical popularity score |
| `MSRP` | Manufacturer's Suggested Retail Price |

---

## 🎯 Objectives

1. **Clean** the raw dataset — handle missing values, fix data types, remove duplicates, and standardize text.
2. **Engineer** new features that make the data more useful for analysis.
3. **Explore** the data through statistics, grouped comparisons, correlation analysis, and visualizations to answer real questions about pricing, performance, and efficiency.

---

## 🛠️ Project Workflow

### 1. Data Cleaning

- Checked the dataset for missing values and decided, column by column, whether to impute, drop, or leave them.
- Converted columns to their correct data types (e.g., `Year`, `Engine HP`, `Engine Cylinders` as numeric).
- Removed duplicate rows.
- Filtered the dataset to vehicles from **1995 and later**.
- Standardized text entries (lower-cased `Vehicle Style` and `Market Category`).

### 2. Feature Engineering

Two new columns were derived from existing ones:

| New Feature | Formula |
|---|---|
| `Total_MPG` | Average of `city mpg` and `highway MPG` |
| `Price_per_HP` | `MSRP / Engine HP` |

### 3. Exploratory Data Analysis (EDA)

- **Descriptive statistics** (mean, median, standard deviation) for `Engine HP`, `MSRP`, `Popularity`, `highway MPG`, and `city mpg`.
- **Group analysis** — average `MSRP` and `Popularity` by `Driven_Wheels`, `Vehicle Size`, and `Engine Cylinders`; average `city mpg` / `highway MPG` by `Engine HP`, `Popularity`, and `MSRP`.
- **Correlation analysis** across `Engine HP`, `MSRP`, `Popularity`, `city mpg`, and `highway MPG`, visualized as a heatmap.

---

## 📊 Visualizations

| Chart | Question it answers |
|---|---|
| Histogram of `city mpg` | How is fuel efficiency distributed across the fleet? |
| Bar chart — average `MSRP` by `Vehicle Size` | Do larger vehicles cost more? |
| Scatter plot — `Engine HP` vs. `MSRP` | Does more horsepower mean a higher price? |
| Boxplot / violin plot — `MSRP` by `Driven_Wheels` | Does drivetrain (FWD/RWD/AWD) affect price? |
| Line plot — `city mpg` & `highway MPG` by `Transmission Type` | How does transmission type affect fuel economy? |
| Correlation heatmap | Which numerical features move together, and how strongly? |

> 📌 *Add your exported chart images to an `images/` folder and reference them here, e.g. `![MSRP by Vehicle Size](images/msrp_by_vehicle_size.png)`.*

**Reading the correlation heatmap:**
- 🟨 **Yellow / bright** cells → strong positive linear correlation
- 🟦 **Dark blue** cells → strong correlation between the numerical features
- 🟩 **Green** cells → weak or non-linear correlation

---

## 💡 Key Insights

> *Replace the bullets below with the specific numbers and observations from your own notebook run.*

- Horsepower and MSRP show a clear positive relationship — higher-powered engines tend to command higher prices.
- Larger vehicle sizes and higher engine-cylinder counts are associated with higher average MSRP.
- Fuel efficiency (`city mpg` / `highway MPG`) tends to move in the opposite direction of horsepower and price — more powerful, pricier cars are generally less fuel-efficient.
- `Popularity` correlates weakly with price and efficiency, suggesting market popularity is driven by factors outside pure specs and cost.
- All-wheel and rear-wheel drive vehicles tend to sit at a higher average price point than front-wheel drive vehicles.

---

## 🧰 Tech Stack

- **Language:** Python 3
- **Data manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook / Google Colab

---

## 📂 Repository Structure

```
car-data-analysis/
├── data/
│   └── car_dataset.csv
├── notebooks/
│   └── car_data_analysis.ipynb
├── images/
│   └── (exported charts)
├── README.md
└── requirements.txt
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/car-data-analysis.git
cd car-data-analysis

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch the notebook
jupyter notebook notebooks/car_data_analysis.ipynb
```

---

## 👤 Author

**Adriana Druta**
Data Analytics student, exploring real-world datasets one project at a time.

📫 [Email](aadry1331@gmail.com)

---

⭐ If you found this project interesting, feel free to star the repo!

