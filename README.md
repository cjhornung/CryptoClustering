# CryptoClustering
Goal: To utilize Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Prepare the Data
- Loaded the data into a Pandas DataFrame
  ![df_market_data](https://github.com/cjhornung/CryptoClustering/assets/134234019/ca13d297-85af-4207-8826-2c711c060170)
- Generated summary statistics
  ![summary_stats](https://github.com/cjhornung/CryptoClustering/assets/134234019/dc635ba8-e758-428c-86a5-9fd5a17c5de8)
- Plotted data to see what's in the DataFrame
  
  ![df_market_data_hvplot](https://github.com/cjhornung/CryptoClustering/assets/134234019/3a98b3c8-d263-4e1c-ba81-11a6dd90eb60)
## Find the Best Value for k Using the Original Scaled DataFrame

- Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  ![elbow_curve](https://github.com/cjhornung/CryptoClustering/assets/134234019/70ccaa0a-112b-4f82-a588-28003bb7a3bf)

Answered the following questions:

- Question: What is the best value for k?

  Answer: The best value for k is 4 because that is the k value where the rate of inertia decrease starts to slow down.
  
## Cluster Cryptocurrencies with K-means Using the Original Scaled Data

- Created a scatter plot using hvPlot by setting `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`.
- Colored the graph points with the labels found using K-Means and add the crypto name in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

  ![price_change_percentage_7d vs price_change_percentage_24h](https://github.com/cjhornung/CryptoClustering/assets/134234019/83bdf367-768e-46f9-8e1e-3bb55b1dd0dc)
## Optimize Clusters with Principal Component Analysis
- Created a DataFrame with the PCA data

   ![pca_data_df](https://github.com/cjhornung/CryptoClustering/assets/134234019/f406ccd3-f18b-4c97-85a6-5b47caeeca78)

## Find the Best Value for k Using the PCA Data
- Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k
  ![pca_elbow_curve](https://github.com/cjhornung/CryptoClustering/assets/134234019/8e8d066d-e2ba-40a6-9637-62fbb83b230d)

Answered the following questions:

- Question: What is the best value for k when using the PCA data?

  Answer: The best value for k is 4 because that is the k value where the rate of inertia decrease starts to slow down.

- Question: Does it differ from the best k value found using the original data?

  Answer: No, they have the same best value for k which is 4. This means that the data sets can be useful for comparative analysis. It suggests that, from a structural perspective, the two datasets can be analyzed or processed in a similar way, as they are believed to have a consistent number of underlying clusters.

## Cluster Cryptocurrencies with K-means Using the PCA Data
- Create a scatter plot using hvPlot by setting  `x="PC1"` and `y="PC2"`. 
- Color the graph points with the labels found using K-Means and added the crypto name in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

   ![PC2 vs PC1](https://github.com/cjhornung/CryptoClustering/assets/134234019/a30be58e-ab49-49a7-bec7-4ebf86401140)

## Visualize and Compare the Results
- Composite plot to contrast the Elbow curves

  ![curve_comparison](https://github.com/cjhornung/CryptoClustering/assets/134234019/0315d6db-cc57-4d62-9a83-7c80505e12db)
- Composite plot to contrast the clusters

  ![cluster_comparison](https://github.com/cjhornung/CryptoClustering/assets/134234019/f31b94f7-8f3c-44fa-a96c-c4131ee090d8)
  
## Conclusion
- The PCA data set resulted in clusters that were less wide spread than the Original data set.
