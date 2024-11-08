# Cryptocurrency Clustering

This project applies clustering analysis to a cryptocurrency dataset to uncover patterns and insights using machine learning techniques. We utilize K-means clustering on both raw and dimension-reduced data (via PCA) to examine trends based on various market indicators.

## Instructions

### Project Overview
The project includes the following main tasks:
- Data loading and preprocessing
- Clustering cryptocurrencies using K-means
- Optimizing cluster count with the elbow method
- Reducing data dimensions with Principal Component Analysis (PCA) for enhanced clustering insights

### File Structure
- `Crypto_Clustering.ipynb`: Main Jupyter Notebook containing code and analysis for cryptocurrency clustering.
- `crypto_market_data.csv`: CSV file containing cryptocurrency market data, including price changes, volumes, and other financial indicators.

### Steps to Run the Analysis

#### 1. Data Preparation
1. **Load Data**: Load `crypto_market_data.csv` into a pandas DataFrame.
2. **Data Exploration**: Generate summary statistics and plot initial visualizations to understand data distribution and trends.

#### 2. Data Normalization
1. **Normalize Data**: Use `StandardScaler()` from scikit-learn to normalize the numerical data.
2. **Create Scaled DataFrame**: Set the `coin_id` as the index and store scaled values in a new DataFrame.

#### 3. K-means Clustering on Scaled Data
1. **Identify Optimal k**: Use the elbow method to determine the optimal number of clusters by:
   - Creating a list of k values (1 to 11).
   - Calculating inertia for each k and plotting an elbow curve.
2. **Cluster Cryptocurrencies**: Use K-means with the optimal k to cluster cryptocurrencies, then visualize clusters with a scatter plot:
   - `x-axis`: `price_change_percentage_24h`
   - `y-axis`: `price_change_percentage_7d`
   - Color each point by cluster label and enable hover to view the `coin_id`.

#### 4. Dimensionality Reduction with PCA
1. **Apply PCA**: Reduce features to three principal components using PCA on the scaled DataFrame.
2. **Variance Analysis**: Calculate explained variance for each component and determine the total explained variance for the three components.

#### 5. K-means Clustering on PCA-Reduced Data
1. **Find Optimal k (PCA Data)**: Repeat the elbow method on PCA data to find the optimal k.
2. **Cluster Cryptocurrencies (PCA Data)**: Run K-means clustering on PCA-reduced data and visualize the clusters:
   - `x-axis`: `PC1`
   - `y-axis`: `PC2`
   - Color by cluster label and add `coin_id` as hover information.

### Analysis and Interpretation
- **Best k Comparison**: Compare the optimal k values derived from scaled vs. PCA data and analyze any differences.
- **Impact of Dimensionality Reduction**: Discuss the impact of using fewer features on clustering accuracy and interpretability.

### Requirements
- Python libraries: `pandas`, `numpy`, `scikit-learn`, `hvPlot`

### License
This project is for educational and non-commercial use. Redistribution and modification are permitted under the project's terms and conditions.
