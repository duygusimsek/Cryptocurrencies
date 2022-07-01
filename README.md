# Cryptocurrencies

## Overview 

In this project, the data of cryptocurrencies were analyzed using the unsupervised machine learning method. A clustering algorithm was used to group the data and hvPlot visualization was used to share the results.

For this analysis;

* The database was preprocessed in order the perform Principal Component Analysis (PCA)
*  The data dimension was reduced by using PCA
* Cryptocurrencies were clustered by using K-Means
* The classification results were visualized with 2D and 3D scatter plots

## Result

### Preprocessing the Data for PCA

Using the Pandas library, the database was preprocessed in order the perform Principal Component Analysis (PCA). For that purpose the following preprocessing steps had been performed on the crypto_df DataFrame:

- The dataset, crypto_data.csv (Add the link here), was retrieved from CryptoCompare (Add the link here). 
- The crypto_df  Pandas DataFrame was created. 
- All the cryptocurrencies that are being traded were kept.
- The “IsTrading“ column was dropped. 
- All the rows that have at least one null value were removed.
- All the rows that do not have coins being mined were removed.
- The “CoinName” column was dropped.

* A new DataFrame was created that stores all cryptocurrency names from the “CoinName” column and retained the index from the crypto_df DataFrame. (add the image here)
* The get_dummies() method was used to create variables for the text features, which were then stored in a new DataFrame, X (add the image here)
* The features from the X DataFrame had been standardized by using the StandardScaler fit_transform() function. (add the image here)



## Resources 

* **Data Source:** crypto_data.csv (Add the link here)
* **Software:**[Python 3.10.2](https://www.python.org/downloads), [Visual Studio Code, 1.65.2](https://visualstudio.microsoft.com/downloads/), [Jupiter Notebook 6.3.0](https://jupyter.org/), Anaconda and Pandas library 
