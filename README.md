# Forecasting-of-Vehicle-Theft-in-Western-Australia
A time-series analysis and predictive modeling project for WA vehicle theft data using Python, Tableau, and Exploratory.io
## 1. About the Data:
- Data is extracted from Crime Statistics which is released by WA Police Force. It is recorded quarterly from 2017 to 2026 mainly for crime monitoring, reporting responsibility.
- The analysis and forecasting is based on the post-Covid period (April 2022 onwards) to avoid significant noise which could affect the forecasting accuracy
- Dataset contains two variables: Time Index (Month-Year) and number of Motor Vehicle theft incidents
<img width="958" height="548" alt="image" src="https://github.com/user-attachments/assets/e3a78d44-82ad-476e-b321-e2ddd3de5bf2" />
## 2. Forecasting Techniques
We compare metric performance of Holt-Winter (HW), Prophet, and SARIMA models that well-capture trend and seasonality appearing in the data. Then, from the comparation, we can choose the best technique to forecast. 
### Holt-Winter (HW)
<img width="736" height="298" alt="image" src="https://github.com/user-attachments/assets/b36b4b8a-d588-4762-afce-2863f3d2cfef" />
HW suggested multiplicative for level, trend and season, implying that the theft levels vary proportionally with the trend. Alpha (0.153), Beta (0.388), and Gamma (0) represent low modification in level, reasonable change in trend, and minimal effect by seasonal fluctuations in the forecast. Regarding the accuracy performance, HW outperforms the simple Naive Approach with its Mean Absolute Scaled Error (MASE) lower than 1 (0.51). This model also provides Root Mean Square Error (RMSE) 34.
### SARIMA
<img width="944" height="111" alt="image" src="https://github.com/user-attachments/assets/f415b5ab-c575-4b5e-9aad-5b2037840e13" />
Exploratory.io has chosen the best SARIMA model that produces RMSE 65.35
### Prophet
<img width="907" height="123" alt="image" src="https://github.com/user-attachments/assets/d3568455-1fd3-448b-b541-c514dcbc5938" />
I used Python to calculate RMSE performance of both addtitive and mulplicative models. The chosen out-of-sample RMSE, which measures how accurately the model predicts data it wasn't trained on, is Mulplicative having RMSE 65.24
** From the perfomance results of Holt-Winter, SARIMA, and Prophet, Holt-Winter is the most realiable forecasting model that better capture the pattern of the test data.  
## 3. Application of Holt-Winter to forecast the vehicle theft trend in next 2 years 
<img width="873" height="490" alt="image" src="https://github.com/user-attachments/assets/f135c37c-9f76-4bd3-ab99-b57b1ae2df5a" />
- The historical crime dataset demonstrates a slight decrease in trend over the period (Apr.2022-Mar.2026), but HW proposes an upturn of theft cases in the next two years (April 2026 to March 2028). 
- This requires WA police to carefully monitor the local situations, reports, and prepare appropriate strategic initiatives to prevent and mitigate the crime’s impact.
- The police can also base on this forecast to coordinate more resources for patrolling, investigating, emmergency responses effectively with associated financial planning
