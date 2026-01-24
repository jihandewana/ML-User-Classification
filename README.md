# ML-User-Classification
Python - User Classification Project by 365 DataScience

# Inspired Source
Detail Case Study 👉 [Machine Learning for User Classification Project](https://learn.365datascience.com/projects/preview/machine-learning-for-user-classification/)

This kind of analysis is a game-changer for any online business. By predicting which users are most likely to upgrade, a company can stop guessing and start reaching out to the right people with the right offers. It’s all about spending the marketing budget more wisely—focusing on the people who will actually find value in the product—which ultimately helps the business grow.

# Key Findings
**📊  Based on EDA**
- To reduce multicollinearity, we used Variance Inflation Factor (VIF) and decided to drop 'practice_exams_started' because it had a high score of 10.2
- To handle missing data, the most frequent value (mode) was used to fill in the eight null entries in the 'student_country' column
- The target variable 'purchased' is imbalanced, with the minority class representing only 9.21% of the data

**🏆 Final Model Comparison & Results**

<img width="385" height="200" alt="image" src="https://github.com/user-attachments/assets/c0d15e6b-cbd6-4d7b-999e-2b76355d7e21" />

**The Verdict: SMOTE is the Game-Changer**
Across the board, applying SMOTE transformed the models' ability to actually find buyers. It significantly boosted Recall and ROC-AUC, proving that balancing the data is non-negotiable for this project.

**The Top Contenders**
- **Support Vector Machines (SMOTE)**: The leader in raw predictive power with the highest ROC-AUC (0.9075). With a Recall of 88.6%, it’s your best bet if you want to catch almost every potential buyer.
- **Random Forests (SMOTE)**: The most reliable all-rounder. It delivered the highest F1-Score (0.7743), striking the perfect balance between finding buyers and maintaining accuracy (72% Precision).
- **Logistic Regression (SMOTE)**: The "Aggressive Hunter." It caught the most buyers (92.3% Recall), though it flags more non-buyers in the process.

**Key Takeaways**
- **Decision Trees**: Surprisingly performed better without SMOTE, suggesting the natural structure was more robust than the oversampled version.
- **KNN**: Showed steady improvement with SMOTE but couldn't quite keep up with the top-tier models.

**🗝️** If you want precision and balance, go with Random Forest. If you want to ensure no buyer is missed, SVM is your winner.

**💡 Conclusion & Business Recommendations**

Based on the model performance, I recommend the following strategies for the 365 platform:
- **Maximize Reach with SVM**: Use the Support Vector Machine model for wide-scale email or notification campaigns. Its 88.6% Recall ensures you capture nearly every student who is on the fence about upgrading.
- **High-Conversion Targeting with Random Forest**: For high-cost interventions (like offering a significant discount or a 1-on-1 consultation), use the Random Forest model. Its superior F1-Score and Precision mean you won't waste resources on users who have no intention of buying.
- **Focus on Engagement**: The data shows that "Minutes Watched" and "Days on Platform" are critical predictors. Marketing efforts should focus on getting free-tier students through their first 3-5 lessons to increase the probability of a "Purchase" trigger.

**🚀 Next Steps**
- **Hyperparameter Tuning**: Further optimize the ccp_alpha for Decision Trees to see if they can beat the ensemble models.
- **Feature Engineering**: Explore if "Time of Day" or "Category of First Course" provides additional lift to the current 0.90 ROC-AUC.
