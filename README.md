# Customer Segmentation Analysis with K-Means Clustering

## 📊 Project Overview

This project performs customer segmentation analysis using K-Means clustering algorithm on marketing campaign data. The goal is to identify distinct customer groups based on their demographic characteristics and purchasing behaviors to enable targeted marketing strategies.

## 🎯 Objectives

- Analyze customer purchase history and demographic data
- Identify optimal customer segments using unsupervised learning
- Provide actionable insights for marketing campaign targeting

## 📁 Dataset

**Source**: [New Marketing Campaign Dataset from Kaggle](https://www.kaggle.com/datasets/mikejimenez24/new-marketing-campaign)

**Dataset Characteristics**:
- **Rows**: 336,006 customer records
- **Columns**: 29 variables
- **Data Types**: Customer demographics, purchase history, campaign responses

### Key Variables:
- **Demographics**: Year_Birth, Education, Marital_Status, Income, Kidhome, Teenhome
- **Purchase Data**: MntWines, MntFruits, MntMeatProducts, MntFishProducts, MntSweetProducts, MntGoldProds
- **Channel Usage**: NumWebPurchases, NumCatalogPurchases, NumStorePurchases, NumWebVisitMonth
- **Campaign Response**: AcceptedCmp1-5, Response, Complain

## 🔧 Methodology

### 1. Data Collection
- Downloaded dataset from Kaggle
- Uploaded to Google Drive for Google Colab access

### 2. Data Exploration
- Comprehensive profiling using `ydata-profiling`
- Correlation analysis to identify relationships
- Data quality assessment

### 3. Data Preprocessing
- **Missing Value Handling**: Removed corrupted records
- **Feature Engineering**: Created new meaningful features
- **Skewness Treatment**: Applied log transformation using `numpy.log1p()`
- **Outlier Detection**: Used IQR method and clipping
- **Categorical Encoding**: One-hot encoding for categorical variables
- **Feature Scaling**: StandardScaler normalization

### 4. Clustering Analysis
- **Algorithm**: K-Means Clustering
- **Optimal Clusters**: Determined using Elbow Method (k=6)
- **Selected Features**: Income, Web_Purchase_Ratio, Age, Total_Purchases, Total_Spend, Has_Children

### 5. Visualization & Analysis
- Cluster distribution plots
- Feature comparison across segments
- Comprehensive segment profiling

## 🏷️ Customer Segments Identified

| Cluster | Segment Name | Key Characteristics |
|---------|--------------|-------------------|
| **0** | Low-Value Family Offline | Family customers, low frequency & spending, primarily offline shopping |
| **1** | High-Value Solo Omnichannel | Single customers, high transactions & spending, mixed online/offline channels |
| **2** | Premium Family Spender | High-income families, frequent transactions, highest total spending |
| **3** | Low-Value Digital Family | Family customers, low spending but higher online shopping ratio |
| **4** | Anomaly High-Value Low-Income | High spending despite low income - requires data validation |
| **5** | Low-Value Solo Offline | Single customers, low frequency & spending, offline dominant |

## 🚀 Getting Started

### Prerequisites
```python
# Required libraries
pandas
numpy
matplotlib
seaborn
scikit-learn
ydata-profiling
```

### Installation
1. Clone this repository:
```bash
git clone https://github.com/AndiRoihan/marketing-campaign-clustering.git
cd marketing-campaign-clustering
```

2. Install required packages:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn ydata-profiling
```

3. Get Dataset in [New Marketing Campaign Dataset from Kaggle](https://www.kaggle.com/datasets/mikejimenez24/new-marketing-campaign)

4. Open the Jupyter notebook or Google Colab:
- **Google Colab**: [Direct Link](https://colab.research.google.com/drive/1RYZyyb3WQY-7twRp6Mv_hIEbpceYvITv?usp=sharing)
- **Local Jupyter**: `jupyter notebook customer_segmentation.ipynb`

## 📊 Technical Implementation

### Feature Engineering:
- `Total_Spend`: Sum of all product category purchases
- `Total_Purchases`: Combined purchase frequency across channels
- `Web_Purchase_Ratio`: Online vs total purchase ratio
- `Age`: Calculated from birth year
- `Has_Children`: Binary indicator for family status

### Model Performance:
- **Clustering Algorithm**: K-Means with k=6
- **Optimization Method**: Elbow Method for optimal cluster selection
- **Feature Selection**: 6 key features for clustering
- **Preprocessing**: Complete pipeline for data quality assurance

## 🔍 Data Quality Issues Addressed

1. **Missing Values**: 1 corrupted record removed
2. **Data Type Corrections**: Fixed Year_Birth format issues
3. **Categorical Standardization**: 
   - Education: Combined "2nd Cycle" with "Master"
   - Marital Status: Grouped ambiguous values ("Absurd", "Alone", "YOLO") as "Other"
4. **Outlier Treatment**: IQR-based detection and clipping
5. **Distribution Normalization**: Log transformation for skewed variables

## 📝 Future Enhancements

- [ ] Implement additional clustering algorithms (DBSCAN, Hierarchical)
