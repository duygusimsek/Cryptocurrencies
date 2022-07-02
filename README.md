# Cryptocurrencies

## Overview 

In this project, the data of cryptocurrencies were analyzed using the unsupervised machine learning method. A clustering algorithm was used to group the data and hvPlot visualization was used to share the results. [crypto_clustering.ipynb](https://github.com/duygusimsek/Cryptocurrencies/blob/main/crypto_clustering.ipynb)

For this analysis;

* The database was preprocessed in order the perform Principal Component Analysis (PCA)
* The data dimension was reduced by using PCA
* Cryptocurrencies were clustered by using K-Means
* The classification results were visualized with 2D and 3D scatter plots

## Result

### 1.Preprocessing the Data for PCA

Using the Pandas library, the database was preprocessed in order the perform Principal Component Analysis (PCA). For that purpose the following preprocessing steps had been performed on the crypto_df DataFrame:

- The dataset, [crypto_data.csv](https://github.com/duygusimsek/Cryptocurrencies/blob/main/crypto_data.csv), was retrieved from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist). :arrow_right: [click here for the image](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_1.1.png)
- The crypto_df Pandas DataFrame was created. 
- All the cryptocurrencies that are being traded were kept.
- The “IsTrading“ column was dropped. 
- All the rows that have at least one null value were removed.
- All the rows that do not have coins being mined were removed.
- The “CoinName” column was dropped. 

* A new DataFrame was created that stores all cryptocurrency names from the “CoinName” column and retained the index from the crypto_df DataFrame. [Image.1.2](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_1.2.png)
* The get_dummies() method was used to create variables for the text features, which were then stored in a new DataFrame, X [Image.1.3](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_1.3.png)
* The features from the X DataFrame had been standardized by using the StandardScaler fit_transform() function. [Image.1.4](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_1.4.png)

### 2.Reducing Data Dimensions Using PCA 

Using the Principal Component Analysis (PCA) algorithm,  the dimensions of the X DataFrame were reduced to three principal components and placed these dimensions in a new DataFrame. [Image.2.1](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_2.1.png)

A new DataFrame named "pcs_df" was created that includes the following columns, PC 1, PC 2, and PC 3, and the index of the "crypto_df" DataFrame was used as the index. [Image.2.2](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_2.2.png)

### 3.Clustering Cryptocurrencies Using K-means

The K-means algorithm was used to cluster the cryptocurrencies using the PCA data, where the following steps had been completed:

* An elbow curve was created using "hvPlot" to find the best value for K. ![Image.3.1](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_3.1.png)
* Predictions were made on the K clusters of the cryptocurrencies’ data [Image.3.2](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_3.2.png)
* A new DataFrame was created with the same index as the “crypto_df“ DataFrame and had the following columns: "Algorithm", "ProofType", "TotalCoinsMined", "TotalCoinSupply", "PC 1", "PC 2", "PC 3", "CoinName", and "Class". [Image.3.3](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_3.3.png)

### 4.Visualizing Cryptocurrencies Results 

By creating scatter plots with Plotly Express and hvplot, the distinct groups were visualized that correspond to the three principal components that were created previously, then a table with all the currently tradable cryptocurrencies was created by using the "hvplot.table()" function. 

The following steps had been completed:

* The clusters were plotted using a 3D scatter plot, and each data point showed the "CoinName" and "Algorithm" on hover. ![Image.4.1](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_4.1.png)
* A table with tradable cryptocurrencies was created using the "hvplot.table()" function [Image.4.2](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_4.2.png)
* The total number of tradable cryptocurrencies was printed, and **there were 532 tradable cryptocurrencies found**. 
* A DataFrame was created that contains the "clustered_df" DataFrame index, the "scaled data", and the "CoinName" and "Class" columns. [Image.4.3](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_4.3.png)
* A hvplot scatter plot was created where the X-axis was "TotalCoinsMined", the Y-axis was "TotalCoinSupply", the data was ordered by "Class", and it showed the “CoinName” when was hovered over the data point [Image.4.4](https://github.com/duygusimsek/Cryptocurrencies/blob/main/Images_cyrpto/Deliverable_4.4.png)

## Resources 

* **Data Source:** [crypto_data.csv](https://github.com/duygusimsek/Cryptocurrencies/blob/main/crypto_data.csv)
* **Data Tool:** [crypto_clustering.ipynb](https://github.com/duygusimsek/Cryptocurrencies/blob/main/crypto_clustering.ipynb)
* **Software:**[Python 3.10.2](https://www.python.org/downloads), [Visual Studio Code, 1.65.2](https://visualstudio.microsoft.com/downloads/), [Jupiter Notebook 6.3.0](https://jupyter.org/), Anaconda and Pandas library 
