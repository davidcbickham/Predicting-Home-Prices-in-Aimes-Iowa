#  Predicting Home Prices in Aimes, Iowa

---

### Problem Statement

According to a 2018 report by the College Baord, the average room and board costs at a public 4-year college reached over $11K, an increase of 3% from 2017. The mission of the DB Realty Group is to provide college students and parents with more cost effective alternatives to on-campus housing. The groups primary strategy is to invest in quaility homes/ apartments near college campuses and to rent them to students at significantly lower costs. The ability to purchase these properties at a low cost is paramount to implementing this strategy. Using the Aimes, Iowa housng data as a case study, the group is seeking to build a model that will allow them to accurately predict housing prices across markets. Additionally, they want to identify the most important attributes of a home that impact the sale price, and which attributes have minimal impact on price. The ideal model will balance the desire for prediction accuracy, with the ability to be generalized to other markets outside of Aimes (i.e. Leverging housing data that can be obtained for other markets).

---

### Executive Summary

Using a Lasso Regression model, we were able to predict home prices in Aimes, Iowa within 24K dollars of the actual sale price (RMSE). The production model produced an R2 test score of 90.1% (training score 90.3%), which means that our model was able to explain 90.1% of the variation in home prices. The features which had the most impact on sale prices included the home sf, the rating of the overall quality of the home/kitchen, the neighborhood, as well as the year it was built. Some notable home features that had no impact on the sale price included the style of roof, the foundation type, and the condition of the basement/exterior of the home (unless they were in the top rated condition).
The model performance had the lowest prediction error for homes which sold for 100-200K (median. sale price was $163K), and higher prediction error for more expensive homes.

---

### Data Overview
The dataset was obtained from the Aimes,Iowa Assessor's Office, and includes data on homes sold form 2006-2010. In addition to the sale price, the dataset includes +80 attributes associated with the home including the above ground sf, neighborhood, number of full bedrooms/bathrooms, etc.

[Data Description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

---

### Key Findings

- The linear regression model with lasso regularization had the lowest RSME of $24K (compared to the Ridge regression RMSE of $25K)

- The Lasso regression model also had a slightly higher R2 score on test data compared the Ridge regression model (90.4% vs. 89.4%)

- While the weights differed, both the Lasso and Ridge model identified a similar set of features that had the greatest impact on the sale price of a home. Those features included the general living area, the overall quality rating of a home, as well as homes with excellent kicthen, basement, and exterior quality.

- Both models correctly identified a positive relationship between homes in the 3 best neighborhoods with the sale price

---

### Summary & Recommendations

In order to replicate this prediction model in the other markets, the DB Realty should focus obtaining the following data points across housing markets: Property measurements (i.e. living area square footage, basement/ garage area, number of bed/bathrooms) anything that indicates the size of the home. These are attributes that were highly predictive during the modeling process and data that is generally available for homes in market. While neighborhood association was useful in predicting sales prices on the Aimes dataset, these are obviously not features that can be applied to other markets. The model aslo demonstrated that qualitative data on the overall quality and condition of the home can also be helpful in predicting sale prices. While helpful, this data can potentially be subjective and may be difficult to standardize across markets. The model performance also suggests that as home prices increases, predictions accuracy tends to suffer. The most accurate investments would be in properties around the median home prices within a given market. If targeting a more expensive market/neighborhood, we recommend using the model cautiously, understanding that there is a greater chance the prediction is below market value.


---

#### Sources

- [2018 College Board College Cost Report](https://trends.collegeboard.org/college-pricing/figures-tables/average-published-undergraduate-charges-sector-2018-19)
- [Data Description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)
