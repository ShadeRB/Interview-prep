Mini-FAQ (rapid-fire answers you can use)

What’s overfitting? Why does it happen?
Memorizing training noise instead of learning general patterns—too many parameters, too long training, or noisy data. Fixed with Dropout, EarlyStopping, regularization, and validation monitoring.

Why joblib/pickle?
To persist models and preprocessors exactly as trained. Then prod can load() and transform/predict identically—no re-fitting, no surprises.

Why SHAP? Any alternatives?
SHAP gives local explanations per prediction and global importance. Alternatives: LIME, Permutation Importance, tree feature_importances_. I like SHAP for business trust and regulator-friendly narratives.

Why SMOTE?
Because with 88/12 skew, a model can game accuracy by predicting “no” for everyone. SMOTE gives the NN enough positive examples to learn meaningful decision boundaries. Always apply it after splitting (otherwise test leakage).

Why One-Hot for NN, LabelEncoder for RF/DT?
NN requires numeric inputs without fake order; One-Hot is correct. Trees are less sensitive but still, One-Hot is cleaner. Your NN path is the production-ready preprocessing; RF/DT scripts are quick baselines.

1. Which tools do you use for data analysis?
Answer:
SQL for data extraction, Python for analysis, and Power BI/Tableau for dashboards.
Example: Pulled transaction data in SQL, analyzed trends in Python, and shared visuals in Power BI.

2. How do you clean messy data?
Answer:
I check for missing values, duplicates, and incorrect formats, then fix them using SQL or Python.
Example: Filled missing “age” values with the median and removed duplicate customer records.

3. How do you handle large datasets?
Answer:
Filter data early, use indexing in SQL, and process in batches.
Example: Reduced query time from 2 hours to 15 minutes by adding proper filters and indexes.

4. How do you explain a technical result to a non-technical audience?
Answer:
I use simple words and visuals. I focus on “what it means” for their decision.
Example: Instead of saying “p-value < 0.05,” I said, “This group responded better to the campaign.”

5. What’s your experience with Azure?
Answer:
I’ve stored data in Azure, used Azure Synapse for queries, and published Power BI dashboards.
Example: Shared a live customer trend report with multiple teams through Azure.

6. How do you prioritize tasks when everything seems urgent?
Answer:
I focus on tasks with the biggest business impact first and confirm priorities with my manager.
Example: Paused a weekly report to finish an urgent churn analysis requested by leadership.

7. How do you check if your analysis is correct?
Answer:
Cross-check results with historical data, validate with teammates, and test on sample data.
Example: Found a reporting error by comparing current revenue trends with last year’s.

8. Give an example of using data to improve customer engagement.
Answer:
Identified that customers active in the first week after signup stayed longer. Suggested onboarding emails, which improved retention by 10%.

9. What’s the biggest data challenge you’ve faced?
Answer:
Working with incomplete data.
Example: Fixed a campaign report by combining multiple data sources to fill in missing customer IDs.

10. How do you make repetitive reports faster?
Answer:
Automate them with Python or schedule queries in SQL.
Example: Cut a 3-hour monthly report to 15 minutes using a Python script.

Typical Data Scientist Rapid-Fire Questions
11. What’s the difference between supervised and unsupervised learning?
Answer:
Supervised uses labeled data (we know the answer), unsupervised finds patterns without labels.
Example: Predicting churn (supervised) vs. grouping customers by behavior (unsupervised).

12. What’s overfitting?
Answer:
When a model learns the training data too well but fails on new data.
Example: A churn model worked great on old data but gave poor results on new customers.

13. What’s feature engineering?
Answer:
Creating new useful variables from existing data.
Example: From “transaction date,” I made “day of week” to find peak shopping days.

14. What’s the purpose of a confusion matrix?
Answer:
It shows how well a classification model predicts.
Example: Used it to see if my churn model had too many false positives.

15. How do you handle imbalanced data?
Answer:
Use techniques like SMOTE, class weights, or focusing on precision/recall.
Example: Balanced churn dataset so the model didn’t always predict “no churn.”