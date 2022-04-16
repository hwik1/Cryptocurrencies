# Cryptocurrency Analysis
Module 18 challenge prepared by Hannah Wikum - April 2022

___
## Resources
Data Source: cyrpto_data.csv (provided from CryptoCompare.com)

Software: Jupyter Notebook, Python 3.7.11 with Pandas, hvPlot, Plotly Express, Scikit-learn
___
## Overview
This analysis was completed for investment bank Accountability Accounting to provide a report on which cryptocurrencies are currently trading on the market, which have been mined, and how they cluster using k-means unsupervised machine learning.

## Methodology
To create the machine learning model and analyze the results I followed a multi-step process:
 * **Preprocessing the data**
    1. Loaded the data from a csv into my Jupyter Notebook
    2. Performed multiple rounds of cleaning to keep only the traded currencies with a working algorithm and coins mined, dropped null values, removed unnecessary columns, and finally converted remaining text columns to numerical values
    3. Standardized remaining data with StandardScaler so the initial size of certain column values wouldn't skew results

 * **Reduced the number of data dimensions using Princpial Component Analysis**
    1. Used Principal Component Analysis (PCA) tools to reduce the remaining data to three key components
    2. Saved the results as a dataframe to be used with k-means

 * **Clustered Cryptocurrencies**
    1. Used k-means to view an elbow curve in order to narrow down the potential amount of clusters (see resulting elbow curve below); narrowed down to four based on chart results

    _Elbow Curve from Using K-Means_
    
    ![image](https://user-images.githubusercontent.com/93058069/163680757-3a2a42e7-8f6e-4192-9136-3f860933531a.png)
    
    2. Ran the k-means model to make classification predictions using  four clusters
    3. Built a new dataframe to collect relevant information for each cryptocurrency, including the three principal component columns, coin name, and class from the k-means analysis
   
  * **Visualized the Results Using 2-D & 3-D Scatter Plots**
    1. Plotted the dataframe from the previous step using the three principal components on the X, Y, and Z axes with unique color/shape by class and a hover box that showed the coin name and algoritm (see below)

    _3-D Scatter Plot_

    ![image](https://user-images.githubusercontent.com/93058069/163680872-4e12180f-1073-4082-a870-542ffc0bc3cc.png)
    
   2. Used hvplot to convert the dataframe to a table listing tradable currencies and the class, with other relevant information about the cryptocurrency (see below)

  _Snippet of Table with Tradable Cryptocurrency_
  
  ![image](https://user-images.githubusercontent.com/93058069/163681332-3c299247-38c0-433d-9068-b75a890bc05b.png)

   3. Scaled the Total Coin Supply and Total Coins Mined columns and plotted the results on a 2-D scatter plot (see below)

  _2-D Scatter Plot_    
  
  ![image](https://user-images.githubusercontent.com/93058069/163681390-5a320aa9-4efb-40d5-a2aa-f653287a9bb3.png)



