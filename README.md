# Problem Statement
## Business Context
Business communities in the United States are facing high demand for human resources, but one of the constant challenges is identifying and attracting the right talent, which is perhaps the most important element in remaining competitive. Companies in the United States look for hard-working, talented, and qualified individuals both locally as well as abroad.

The Immigration and Nationality Act (INA) of the US permits foreign workers to come to the United States to work on either a temporary or permanent basis. The act also protects US workers against adverse impacts on their wages or working conditions by ensuring US employers' compliance with statutory requirements when they hire foreign workers to fill workforce shortages. The immigration programs are administered by the Office of Foreign Labor Certification (OFLC).

OFLC processes job certification applications for employers seeking to bring foreign workers into the United States and grants certifications in those cases where employers can demonstrate that there are not sufficient US workers available to perform the work at wages that meet or exceed the wage paid for the occupation in the area of intended employment.

## Objective
In FY 2016, the OFLC processed 775,979 employer applications for 1,699,957 positions for temporary and permanent labor certifications. This was a nine percent increase in the overall number of processed applications from the previous year. The process of reviewing every case is becoming a tedious task as the number of applicants is increasing every year.

The increasing number of applicants every year calls for a Machine Learning based solution that can help in shortlisting the candidates having higher chances of VISA approval. OFLC has hired the firm EasyVisa for data-driven solutions. You as a data scientist at EasyVisa have to analyze the data provided and, with the help of a classification model:

## Facilitate the process of visa approvals.
Recommend a suitable profile for the applicants for whom the visa should be certified or denied based on the drivers that significantly influence the case status.

## Actionable Insights and Recommendations

- The best performing model was the Over sampled Gradiant Boost model with hyper parameter tuning.
- This model had an F1 score of 80.05% and a Delta score of .01%

# Conclusion

In this project, I performed exploratory data analysis and built several machine learning models to predict visa application status from the initial dataset.

## Model Validation:
The project began with EDA on the raw data, where I handled missing values and converted categorical features into numerical form. The dataset was then split into training and testing subsets for model evaluation.

## Model Building:
Model development was completed in three stages.

1. Initial Models: I trained five different models on the original training data and saved the best-performing one for later analysis.
2. Over-Sampled Models: I applied oversampling to address class imbalance and retrained the same five models, again retaining the best results.
3. Under-Sampled Models: I repeated the process with under-sampled data and compared performance across all sections.

After evaluating all models, I identified which were overfit and which generalized well. The strongest performers were the Gradient Boosting model on the over-sampled data and the AdaBoost model on the original dataset.

## Model Tuning:
I conducted two rounds of hyperparameter tuning. In the first round, I adjusted parameters manually to reduce overfitting and achieve balanced performance across models. In the second round, I performed a formal grid search on the top-performing model to further optimize its accuracy and efficiency.

## Final Results:
The final top-performing models were:

- Gradient Boost (Over-Sampled)
- AdaBoost (Over-Sampled)
- Decision Tree (Over-Sampled, manually tuned)
- Gradient Boost (Under-Sampled)

A formal grid search was performed on the top model which was the Gradiant Boost Over-Sampled model.
The performance differences between the manually tuned model and the grid search was under 1% which I felt was a small enough margin that additional tuning was unessesary.

Overall, the Gradient Boosting model on over-sampled data provided the best balance between precision and recall, making it the most suitable model for predicting visa application outcomes.

## Future Improvements
- It would be possible to create an ensemble model using the top 5 existing models.

### Final Thoughts
- For future projects I will replace the model validation function from test train delta to k-fold cross validation.
- If I had stored all the models in a single dataframe from the beginning of the project it would have made future data processing much easier.

### Project Dependencies
- Python Version: 3.13
- numpy==2.3.2
- pandas==2.3.1
- scikit-learn==1.5.2
- matplotlib==3.10.6
- seaborn==0.13.2
- xgboost==3.0.5**