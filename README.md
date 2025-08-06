📊 Early Termination Analysis of Term Deposits  
(Using Kaplan-Meier & Cox Model)

This project uses two survival analysis techniques to model early termination risk of term deposits:

- 📉 Kaplan-Meier Estimator: Visualizes survival probability over time.  
- 📈 Cox Proportional Hazards Model: Estimates the effect of explanatory variables on the risk.

🛠 Libraries
pandas  
matplotlib  
sksurv  
sklearn

📂 Data Summary
- sure: Actual duration  
- erken_kapama: 1 = early terminated, 0 = matured as planned  
- Others: customer type, currency, interest rate, etc.

📌 Key Code

Kaplan-Meier
from sksurv.nonparametric import kaplan_meier_estimator  
time, surv_prob = kaplan_meier_estimator(df["erken_kapama"] == 1, df["sure"])

Cox Model
from sksurv.linear_model import CoxPHSurvivalAnalysis  
model = CoxPHSurvivalAnalysis().fit(X, y)

✅ Output
- Kaplan-Meier: shows time-based early closure risk.  
- Cox: reveals drivers of early termination (e.g., TL deposits may be more likely to terminate early).
