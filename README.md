# Evoastra Major Project – Energy Consumption Time-Series Analysis

## 📌 Project Overview

This is a comprehensive **data analysis and machine learning project** focused on **energy consumption patterns**, **time-series analysis**, and **anomaly detection** using multi-utility building energy data.

The objective is to understand **energy usage trends**, **consumption patterns**, **peak demand periods**, and **detect anomalies** in building energy systems using real-world time-series data.

The project follows a structured data pipeline:

1. Data Collection & Exploration  
2. Data Cleaning & Preprocessing  
3. Feature Engineering  
4. Anomaly Detection  
5. Data Visualization & Reporting  

---

## 🎯 Project Objectives

- Load and explore multi-utility energy datasets  
- Clean and preprocess time-series data  
- Engineer meaningful temporal and statistical features  
- Detect anomalies in energy consumption patterns  
- Analyze consumption trends across utilities  
- Visualize insights and patterns  
- Generate actionable reports for energy optimization


---

## 🛠️ Technologies Used

- **Python** – core programming language  
- **Pandas** – data manipulation and processing  
- **NumPy** – numerical computing  
- **Scikit-learn** – preprocessing and machine learning  
- **Matplotlib / Seaborn** – data visualization  
- **Jupyter Notebook** – interactive analysis and documentation  
- **Markdown** – documentation and reporting  

---

## 📁 Project Folder Structure

```
Evoastra_major_project/
├── README.md
├── Evoastra/
│   ├── Major_project_main.ipynb        # Main analysis notebook
│   ├── *_cleaned.csv                   # Cleaned datasets (9 utilities)
│   ├── data/
│   │   ├── raw/                        # Raw energy datasets
│   │   │   ├── electricity.csv
│   │   │   ├── gas.csv
│   │   │   ├── water.csv
│   │   │   ├── solar.csv
│   │   │   ├── steam.csv
│   │   │   ├── chilledwater.csv
│   │   │   ├── hotwater.csv
│   │   │   ├── irrigation.csv
│   │   │   ├── weather.csv
│   │   │   ├── metadata.csv
│   │   │   └── energy_subset.csv
│   │   └── processed/
│   │       └── features_energy.csv    # Feature-engineered dataset
│   ├── models/                         # ML models
│   ├── results/                        # Analysis outputs
│   │   ├── anomalies.csv              # Detected anomalies
│   │   └── Graphs/                    # Visualizations
│   └── .ipynb_checkpoints/
```

---

## 🔍 Data Description

The dataset contains **multi-utility energy consumption data** from building systems:

| Utility | Description | Source File |
|---------|-------------|-------------|
| **Electricity** | Primary electrical energy consumption | electricity.csv |
| **Gas** | Natural gas for heating and appliances | gas.csv |
| **Water** | Total water consumption | water.csv |
| **Solar** | On-site solar generation output | solar.csv |
| **Steam** | HVAC and process heating | steam.csv |
| **Chilled Water** | Cooling system energy usage | chilledwater.csv |
| **Hot Water** | Hot water consumption | hotwater.csv |
| **Irrigation** | Outdoor watering systems | irrigation.csv |
| **Weather** | Environmental conditions (temperature, humidity, etc.) | weather.csv |

Each dataset contains:
- **Timestamp**: Date and time of measurement
- **Multiple meters/sensors**: Data from different building zones or measurement points
- **Numeric values**: Energy consumption/generation in standardized units

---

## 🧹 Data Cleaning Steps

The cleaning process ensures data quality and consistency:

1. **Timestamp Conversion** – Convert string timestamps to datetime format
2. **Sorting** – Sort data chronologically by timestamp
3. **Deduplication** – Remove duplicate entries
4. **Missing Value Handling** – Forward fill and backward fill for temporal continuity
5. **Outlier Detection** – Identify and flag suspicious values
6. **Data Normalization** – Apply MinMax scaling (0-1 range)
7. **Dataset Integration** – Combine all utilities into unified time-indexed structure
8. **Validation** – Verify cleaned data integrity

Output: Cleaned datasets saved as "cleaned.csv" files

---

## 🔧 Feature Engineering Process

Transform raw time-series data into predictive features:

### Temporal Features
- **Hour of Day** (0-23) – Captures daily consumption cycles
- **Day of Week** (0-6) – Identifies weekly patterns
- **Month/Season** – Seasonal trends in energy usage

### Statistical Features
- **24-hour Rolling Mean** – Smooths daily trends
- **24-hour Rolling Std Dev** – Measures hourly variability
- **Lag-1 Features** – Previous hour's consumption for temporal dependency

### Aggregation
- **Mean across meters** – Unified consumption per utility type
- **Peak/Minimum values** – Identifies demand extremes

### Data Preparation
- Remove first 24 rows (NaN from lag features)
- Scale features for ML models
- Create train/test splits

Output: `data/processed/features_energy.csv` with 20+ engineered features

---

## 📊 Analysis Performed

1. **Temporal Pattern Analysis**
   - Daily consumption cycles
   - Weekly trends and peak hours
   - Seasonal patterns

2. **Correlation Analysis**
   - Cross-utility relationships (electricity vs. gas vs. water)
   - Weather impact on energy consumption
   - Building occupancy patterns

3. **Anomaly Detection**
   - Statistical outlier identification
   - Unusual consumption patterns
   - Equipment malfunction detection

4. **Consumption Metrics**
   - Peak demand periods
   - Average consumption rates
   - Consumption variability

---

## 📈 Visualizations & Outputs

Key insights presented as:

- **Time-series plots** – Consumption trends over time
- **Distribution charts** – Frequency and range analysis
- **Heatmaps** – Temporal patterns (hour × day of week)
- **Anomaly plots** – Flagged unusual events
- **Correlation matrices** – Utility relationships

All visualizations saved in `results/Graphs/` folder

---

## ✅ Quality Assurance & Testing

The quality assurance phase ensures accuracy, stability, and reproducibility:

- ✓ Verified data loading across all 9 utility datasets
- ✓ Tested missing value handling (forward/backward fill)
- ✓ Validated timestamp conversion and time-series alignment
- ✓ Confirmed MinMax scaling application
- ✓ Verified feature engineering without runtime errors
- ✓ Tested anomaly detection algorithms
- ✓ Validated visualization generation
- ✓ Confirmed output file integrity
- ✓ Ensured reproducible results across multiple runs

**QA Status:** All pipeline stages validated and ready for production use.

---

## 📈 How to Run the Project

### Prerequisites
```bash
Python 3.7+
Jupyter Notebook
```

### Installation

1. **Clone/Download the project**
    ```bash
    cd Evoastra_major_project
    ```

2. **Install required packages**
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn jupyter
    ```

3. **Open the main notebook**
    ```bash
    jupyter notebook Evoastra/Major_project_main.ipynb
    ```

4. **Run cells sequentially** to execute:
   - Data loading and exploration
   - Data preprocessing and cleaning
   - Feature engineering
   - Anomaly detection
   - Visualization and reporting

---

## 💡 Key Insights & Use Cases

### Potential Applications
- **Energy Optimization** – Identify and reduce peak consumption periods
- **Predictive Maintenance** – Detect equipment failures through anomalies
- **Sustainability Tracking** – Monitor renewable energy vs. consumption
- **Building Management** – Optimize HVAC and utility operations
- **Cost Reduction** – Identify opportunities to lower operational expenses
- **Demand Forecasting** – Predict future energy needs
- **Benchmarking** – Compare consumption against similar buildings

---

## 📝 Reports & Documentation

- **Major_project_main.ipynb** – Complete analysis workflow
- **README.md** – Project overview and instructions
- **results/anomalies.csv** – Detected anomalies with timestamps
- **results/Graphs/** – All visualization outputs

---

## 🔄 Data Processing Pipeline

```
Raw Data (9 Utilities)
    ↓
Load & Explore
    ↓
Timestamp Parsing & Indexing
    ↓
Missing Value Handling (Forward/Backward Fill)
    ↓
Data Cleaning & Validation
    ↓
Feature Engineering (Temporal, Statistical, Lag)
    ↓
Scaling & Normalization
    ↓
Anomaly Detection
    ↓
Visualization & Reporting
    ↓
Results (CSV + Graphs)
```

---

## 📌 Important Notes

- **Data Alignment** – All utilities time-aligned using datetime index
- **NaN Handling** – Forward/backward fill maintains temporal continuity
- **Scaling** – MinMax normalization (0-1 range) applied to all features
- **Memory Optimization** – Core operations limited to first 5 energy columns
- **First 24 Rows** – Removed due to NaN from lag operations
- **Reproducibility** – All operations logged and documented

---

## 🚀 Future Enhancements

- [ ] Implement LSTM neural networks for time-series prediction
- [ ] Add Isolation Forest and LOF for advanced anomaly detection
- [ ] Build real-time monitoring dashboard
- [ ] Integrate weather normalization
- [ ] Develop forecasting models (ARIMA, Prophet)
- [ ] Add comparative analysis across multiple buildings
- [ ] Create automated reporting system
- [ ] Deploy as web application

---

## ✅ Conclusion

This project demonstrates a **complete end-to-end data pipeline** for energy consumption analysis. It applies industry best practices in data handling, feature engineering, and analytical reporting. The results provide actionable insights for building energy optimization and sustainability initiatives.

---
