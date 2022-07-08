# Cryptocurrencies

## Overview: 

For this week we are using a data set consisting of cryptocurrency data to provide investing opportunities in cryptocurrency.  This project aims to show what currencies are available for trade in the market.  As this data is less than ideal we will use unsupervised machine learning to process this data.  The data will be grouped and clustered using the machine learning algorithms and also visualize with hvplot.


## Results:

   - Deliverable 1 Preprocessing the Data for PCA:

     - Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.
     - Keep all the cryptocurrencies that are being traded.
     - Drop the IsTrading column.
     - Remove rows that have at least one null value.
     - Filter the crypto_df DataFrame so it only has rows where coins have been mined.
     - Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
     - Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.

      ![This is an image](https://github.com/BMoreland20/Cryptocurrencies/blob/main/Resources/deliverable1.png)


   - Deliverable 2 Reducing Data Dimensions Using PCA:

     - Continue using the crypto_clustering.ipynb file from Deliverable 1 where you’ve already performed the preprocessing steps.
     - Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.
     - Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.

      ![This is an image](https://github.com/BMoreland20/Cryptocurrencies/blob/main/Resources/deliverable2.png)


   - Deliverable 3 Clustering Crytocurrencies Using K-Means:
     - Continue using the crypto_clustering.ipynb file that you used in Deliverable 2 to reduce the dataset to three dimensions.
     - Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.
     - Next, use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.
     - Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.
     - Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.
     - Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.

      ![This is an image](https://github.com/BMoreland20/Cryptocurrencies/blob/main/Resources/deliverable3.png)


   - Deliverable 4 Visualizing Cryptocurrencies Results:
     - Continue using the crypto_clustering.ipynb file from Deliverable 3 where you have predicted the K clusters for the cryptocurrencies’ data.
     - Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
     - Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.
     - Create a table with tradable cryptocurrencies using the hvplot.table() function.

      ![This is an image](https://github.com/BMoreland20/Cryptocurrencies/blob/main/Resources/deliverable4.1.png)
 
     - Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.
     - Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.
     - Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.
     - Add the CoinName column from the clustered_df DataFrame to the new DataFrame.
     - Add the Class column from the clustered_df DataFrame to the new DataFrame.

      ![This is an image](https://github.com/BMoreland20/Cryptocurrencies/blob/main/Resources/deliverable4.2.png)
 
     - Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data point.

      ![This is an image](https://github.com/BMoreland20/Cryptocurrencies/blob/main/Resources/deliverable4.3.1.png)



## Summary:


