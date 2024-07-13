# **Intermediate-ML- Housing**

---------------------
![image_2024-07-13_152913981](https://github.com/user-attachments/assets/65164a8c-c2ca-4ba4-ae60-24dcffcb5922)

------------------------------------------
- The Problem A house-flipping company would like to identify underpriced homes by comparing asking prices to predicted sale prices. They would like to segment homes into groups to analyze what kinds of homes there are. They would also like a model that predicts the selling price of a home.

------------------------------------
-  **KMeans Clusters**

    - Choosing number o clusters:
      ![download](https://github.com/user-attachments/assets/cb8d70e0-d157-4a18-885c-46b7787f680f)
      - The above line plot shows that the graph starts to level off at 3 clusters. there is an elbow on cluster 3 , but 5 clusters might be another suitable choice for a good number of clusters.
     
    - Clustering Report Analysis:
      ![download (25)](https://github.com/user-attachments/assets/39c720e9-b9a0-4b2f-a97f-d0ea4c05a584)


      

        - Cluster 0: cluster 0 represent lower-priced homes with moderate living space.

            - Average Sale Price: $351,182.
            - Average Total Living Area: 1,539 sqft.
            - Average Year Built: 1961.
              
        - Cluster 1: Cluster 1 represent mid-priced homes with larger living space.
 
          - Average Sale Price: $774,380.
          - Average Total Living Area: 2,063 sqft.
          - Average Year Built: 1979.
            
        - Cluster 2: cluster 2 represents higher-priced homes with the largest living space.

          - Average Sale Price: $1,565,258.
          - Average Total Living Area: 3,061 sqft.
          - Average Year Built: 1974.
            
       - Cluster 3: cluster 3 represents moderately-priced homes with moderate living space.

          - Average Sale Price: $575,224
          - Average Total Living Area: 1,807 sqft
          - Average Year Built: 1974
            
      - Cluster 4: cluster 4 represents higher-priced homes with large living space and modern features.

        - Average Sale Price: $1,092,419
        - Average Total Living Area: 2,576 sqft
        - Average Year Built: 1973
          
      - **Important Differences between Clusters**: Sale Price vs. Total Living Area:

        - these clusters graphs illustrate the relationship between sale price and total living area for each cluster. It shows how clusters are differ in terms of pricing and living space.where incrasing in total living area increase the sales price increased.
          
----------------------------

- **Deep Learning Models:**

  - Model 1 :
      - In the first model , we will use the following as a first step in building the model:
        - Inpuer layer: 1
        - hidden layers: 2
        - Ealry stopping = 10.
        - Dropout = 20%.
        - Epoch: 50.

    ![download (26)](https://github.com/user-attachments/assets/c23b31fe-98af-4a65-92fd-a572128d7bca)

     `The plot indicated that the model is still learning,
          there is a room to fix it in the next models`

    - Model 2 :
      - In this model, in this model will try tuning using l1/l2 regularizer to decrase overfiting from model 2.
In the third model , we will use the following as a first step in building the model:
        - Inpuer layer: 1
        - hidden layers: 1
        - Ealry stopping = 20.
        - Dropout = 20%.
        - Epoch: 200.
       
      ![download (28)](https://github.com/user-attachments/assets/b70ce408-f9d4-42e1-b0a5-60b486eb9575)
      
   `there is a significant improvement after using l1/l2 regularizer , and overfitting issue handeld better and the stabilization of loss has been achieved.`

  ----------------------------------------------------------------

- **Comparing models**

  - Model 1:

    - R2: it explains that 54% of the variance in the target variable.

    - MAE: the model tends to make an error of around $138,760 in predicting home selling price.

    - RMSE: our model predictions make an error of from the actual selling prices by around $198,574.

  - Model 2:

    - R2: it explains that 55% of the variance in the target variable.

    - MAE: the model tends to make an error of around $138,287 in predicting home selling price.

    - RMSE: our model predictions make an error of from the actual selling prices by around $197,089.

  - Model 3:

    - R2: it explains that 55% of the variance in the target variable.

    - MAE: the model tends to make an error of around $139,407 in predicting home selling price.

    - RMSE: our model predictions make an error of from the actual selling prices by around $198,667.

- The best model is model 2 in comparing to loss plots history and metrics results, where it achieves stabilization in the loss.
the result from the model 2:

    - It has the highest R2 score (55%), indicating it explains slightly more variance in the target variable compared to the other models.

    - It has the lowest MAE ($138,287), indicating it makes the smallest average error in predictions.

    - It has the lowest RMSE ($197,089), indicating its predictions are closest to the actual values on average.

    - the model was trained with the following parametrs:

- focus metric:
  - RMSE

------------------------------------------------------- 

- **Based on our model's performance metrics, here's how effectively it addresses the business problem:**

  - Identifying Undervalued Properties:

    - Our model effectively identifies properties that are likely priced below their actual market value. This capability allows the company to focus on promising investment opportunities where higher profits can be realized.
      
  - Segmentation and Analysis:

    - By segmenting properties based on price predictions and relevant criteria, the company gains insights into different market segments. This differentiation helps in making better strategic decisions, such as targeting specific customer segments or enhancing marketing efforts.
      
  - Predicting Selling Prices:

    - The model's ability predict selling prices enables the company to make informed decisions regarding property acquisition and sales strategies. This reduces the negative impact of pricing uncertainty and increases profitability by minimizing the risk of overpaying for properties.
      

  - Identifying Undervalued Properties:

    - Our model effectively identifies properties that are likely priced below their actual market value. This capability allows the company to focus on promising investment opportunities where higher profits can be realized.
Segmentation and Analysis:

    - By segmenting properties based on price predictions and relevant criteria, the company gains insights into different market segments. This differentiation helps in making better strategic decisions, such as targeting specific customer segments or enhancing marketing efforts.

  - Predicting Selling Prices:

    - The model's ability predict selling prices enables the company to make informed decisions regarding property acquisition and sales strategies. This reduces the negative impact of pricing uncertainty and increases profitability by minimizing the risk of overpaying for properties.
Overall, our model provides a foundation for solving the business problem by accurately forecasting property selling prices, identifying investment opportunities, and supporting strategic decision-making in real estate investments.

-----------------------------------------------
