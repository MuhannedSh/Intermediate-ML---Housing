# **Intermediate-ML- Housing**

----------------------------------------------------------------

![image_2024-07-13_152913981](https://github.com/user-attachments/assets/65164a8c-c2ca-4ba4-ae60-24dcffcb5922)

- The Problem A house-flipping company would like to identify underpriced homes by comparing asking prices to predicted sale prices. They would like to segment homes into groups to analyze what kinds of homes there are. They would also like a model that predicts the selling price of a home.

----------------------------------------------------------------
 # **KMeans Clusters**
----------------------------------------------------------------

- ## **Choosing number o clusters**:
  ![download](https://github.com/user-attachments/assets/cb8d70e0-d157-4a18-885c-46b7787f680f)
      `The above line plot shows that the graph starts to level off at 3 clusters. there is an elbow on cluster 3 , but 5 clusters might be another suitable choice for a good number of clusters.`
     
- ## **Clustering Report Analysis**:
  ![download (29)](https://github.com/user-attachments/assets/6152d9b8-2826-48c3-98b6-e4161e12ef88)



      

- **Cluster Analysis Report:**
  - Cluster 0: Cluster 0 represents lower-priced homes with moderate living space.

    - Average Sale Price: $692,398
    - Average Total Living Area: 1,561 sqft
    - Average Year Built: 2014

  - Cluster 1: Cluster 1 represents mid-priced homes with larger living space.

    - Average Sale Price: $535,318
    - Average Total Living Area: 1,441 sqft
    - Average Year Built: 1947

  - Cluster 2: Cluster 2 represents higher-priced homes with the largest living space.

    - Average Sale Price: $715,733
    - Average Total Living Area: 2,338 sqft
    - Average Year Built: 1963

  - Cluster 3: Cluster 3 represents moderately-priced homes with moderate living space.

    - Average Sale Price: $726,505
    - Average Total Living Area: 1,616 sqft
    - Average Year Built: 2017

  - Cluster 4: Cluster 4 represents higher-priced homes with large living space and modern features.

    - Average Sale Price: $870,445
    - Average Total Living Area: 2,962 sqft
    - Average Year Built: 2003

- **Important Differences between Clusters**: Sale Price vs. Total Living Area

These clusters provides the visualization of sale price vs total living area. These are graphs illustrating the comparison of clusters
 per pricing / living area, showing that generally a higher total living area is also related to a higher sales price
          
----------------------------------------------------------------
## **Deep Learning Models:**
----------------------------------------------------------------

-
    - **Model 1 :**
       - In model 2 , we will increase number of epochs,and get a sense of when the model loss and metrics be satisfied:
            - Inpuer layer: 1
            - hidden layers: 2
            - Ealry stopping = 10.
            - Dropout = 20%.
            - Epoch: 50.
        
   ![download (30)](https://github.com/user-attachments/assets/948688a9-1d18-45c7-a892-b488962d08f1)


     `The plot indicated that the model is still learning,
          there is a room to fix it in the next models`
        

         
    - **Model 2 :**
       - In model 2 , we will increase number of epochs,and get a sense of when the model loss and metrics be satisfied:
            - Inpuer layer: 1
            - hidden layers: 1
            - Ealry stopping = 10.
            - Dropout = 20%.
            - Epoch: 100.
       
      ![download (31)](https://github.com/user-attachments/assets/0f674ccf-febf-4142-aac6-4f92bc462170)


    - **Model 3 :**
      -  In this model, in this model will try tuning using l1/l2 regularizer to decrase overfiting from model 2:
            - Inpuer layer: 1
            - hidden layers: 2 , in order to allows the model to learn more complex patterns.
            - Ealry stopping = 20 in order to helps the model to prevent premature stopping by giving the model more time to improve
        -  Dropout = 20%.
        - Epoch: 200.


    ![download (32)](https://github.com/user-attachments/assets/bc51eb97-98d9-4a65-a286-fa76ff503f7d)

     `there is a significant improvement after using l1/l2 regularizer , and overfitting issue handeld better and the stabilization of loss has been achieved.`



    - **Model 4 :**
      -  In this model, I will try decreasing hidden layers in order to reduce complexity and fix the overfitting issue in model 3.:
            - Inpuer layer: 1
            - hidden layers: 2
            - Ealry stopping = 8
            -  Dropout = 20%.
            - Epoch: 60.


          =![download (33)](https://github.com/user-attachments/assets/3e65995b-d5f4-4bc9-8b04-a345e5482c69)

----------------------------------------------------------------
## **Comparing models**
----------------------------------------------------------------

- **Model 1:**

------------------------------------------------------------
| Dataset        | RMSE          | MAE           | R2        |
|----------------|---------------|---------------|-----------|
| **Testing**    | 197,709.1176  | 138,280.3440  | 0.5527    |
| **Training**   | 141,532.0892  | 95,575.7123   | 0.7755    |
------------------------------------------------------------


- **Model 2:**

------------------------------------------------------------
| Dataset        | RMSE          | MAE           | R2        |
|----------------|---------------|---------------|-----------|
| **Testing**    | 197,481.9082  | 137,962.4054  | 0.5538    |
| **Training**   | 134,860.6538  | 89,514.6594   | 0.7962    |
------------------------------------------------------------

- **Model 3:**
  

-----------------------------------------------------------
| Dataset        | RMSE          | MAE           | R2        |
|----------------|---------------|---------------|-----------|
| **Testing**    | 204,872.2002  | 143,596.0998  | 0.5197    |
| **Training**   | 117,365.8708  | 74,162.2296   | 0.8456    |
------------------------------------------------------------


- **Model 4:**

------------------------------------------------------------
| Dataset        | RMSE          | MAE           | R2        |
|----------------|---------------|---------------|-----------|
| **Testing**    | 206,072.8831  | 144,085.6794  | 0.5141    |
| **Training**   | 169,018.0594  | 115,380.4149  | 0.6798    |
------------------------------------------------------------



- **Model 4 stands out as the best choice:**

  - Model 4 achieves an RMSE of 206,072.88 on the testing dataset, indicating its predictions are relatively close to the actual home selling prices on average..

  - With a low validation (testing) loss the model shows effective handling of the predictive task, minimizing the overall error in forecasting.



- **Overfitting Consideration:**

Model 4 Performance: Model 4 shows balanced performance between training and testing datasets, reflected in its consistent metrics across both sets.

-----------------------------------------------


- **Based on our model's performance metrics, here's how effectively it addresses the business problem:**
  - Accurate Predictions: Model 2 achieves an RMSE of 206,072.88 on the testing data, indicating its predictions are relatively close to the actual home selling prices on average. This precision facilitates precise decision-making in property transactions.

  - Variance Explanation: The model achieves an R2 score of 51.41%, indicating it explains a significant portion of the variability in home prices. This insight into market dynamics is crucial for strategic planning in real estate investments.

  - Generalization: Model 2 demonstrates consistent performance across datasets, highlighting its robust generalization capability. This consistency ensures dependable predictions that can adapt to different market conditions, enhancing stakeholders' confidence in its applicability.
