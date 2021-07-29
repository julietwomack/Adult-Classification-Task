The present classification task is to predict whether someone makes over $50k per year or not based on 1994 census data. The dataset was retrieved from the UCI Machine Learning Repository at the following [link](https://archive.ics.uci.edu/ml/datasets/adult). The dataset has 32,561 rows and 15 columns:

<details>
<summary>Features:</summary>

```
| Variable         | Type        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Age              | Numerical   | Age of individuals between 17 to 90 years old.                                                                                                                                                                                                                                                                                                                                                                                               |
| Work_class       | Categorical | Either private, self-emp-not-inc, local-gov,?, state-gov, self-emp-inc, federal-gov, without-pay, never-worked.                                                                                                                                                                                                                                                                                                                              |
| Fnlwgt           | Numerical   | Continuous variable to describe the proportion of the population that may fit the characteristics.                                                                                                                                                                                                                                                                                                                                           |
| Education        | Categorical | Either HS-grad, some-college, Bachelors, Masters, Assoc-voc, 11th, Assoc-acdm, 10th, 7th-8th, Prof-school, 9th, 12th, Doctorate, 5th-6th, 1st-4th, or Preschool.                                                                                                                                                                                                                                                                             |
| Education_num    | Numerical   | An integer value associated with Education feature.                                                                                                                                                                                                                                                                                                                                                                                          |
| Marital_status   | Categorial  | Either married-civ-spouse, never-married, divorced, separated, widowed, married-spouse-absent, or married-AF-spouse.                                                                                                                                                                                                                                                                                                                         |
| Occupation       | Categorical | Either prof-specialty, craft-repair, exec-managerial, adm-clerical, sales, other-service, machine-op-inspct, ?, transport-moving, handlers-cleaners, farming-fishing, tech-support, protective-serv, priv-house-serv, or armed-Forces                                                                                                                                                                                                        |
| Relationship     | Categorical | Either husband, not-in-family, own-child, unmarried, wife, or other-relative.                                                                                                                                                                                                                                                                                                                                                                |
| Race             | Categorical | Either White, Black, Asian-Pac-Islander, Amer-Indian-Eskimo, or Other.                                                                                                                                                                                                                                                                                                                                                                       |
| Sex              | Categorial  | Either Male or Female.                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Capital_gain     | Numerical   | Individual monetary profit.                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Capital_loss     | Numerical   | Individual monetary loss.                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Hours_per_week   | Numerical   | Number of hours working per week.                                                                                                                                                                                                                                                                                                                                                                                                            |
| Native_country   | Categorical | Either United-States, Mexico, ?, Philippines, Germany, Canada, Puerto-Rico, El-Salvador, India, Cuba, England, Jamaica, South, China, Italy, Dominican-Republic, Vietnam, Guatemala, Japan, Poland, Columbia, Taiwan, Haiti, Iran, Portugal, Nicaragua, Peru, Greece, France, Ecuador, Ireland, Hong, Trinadad&Tobago, Cambodia, Laos, Thailand, Yugoslavia, Outlying-US(Guam-USVI-etc), Hungary, Honduras, Scotland, or Holand-Netherlands. |
| Native_continent | Categorical | Featured engineered variable created from Native_country for the modified training dataset. Either North America, Europe, Not known, South America, or Asia.                                                                                                                                                                                                                                                                                 |
```
</details>

<details>
<summary>The analysis is divided into the following sections:</summary>

````
 1. Descriptive statistics
 2. Visualizations
 3. Split into test/train sets
 4. Data encoding
 5. Spot checking algorithms with untransformed and transformed data
 6. Fine tuning model using training set
 7. Ensemble methods with untransformed and transformed data
 8. Feature engineering on a copy of the train/test sets
 9. Spot checking algorithms with untransformed and transformed data
 10. Ensemble methods with untransformed and transformed data
 11. Fine tuning model using modified training set 
 12. Finalizing model
 ````
</details>

The following packages were used for the analysis:

- Numpy
- Pandas
- Matplotlib
- Seaborn
- Sci-kit learn

**General conclusions from the analysis:**

- The logistic regression model had the highest accuracy among all k-fold cross validations (k = 10) with the untransformed and transformed training sets (unmodified/full and modified train set).
- Although the Gradiant Boosting Classifier had a higher accuracy  (about 86%) than the logistic regression model, the logistic regression model, a simpler model overall, fitted on the modified training set was selected as the final model.
- The final model had an accuracy of 85.5%.
- The final model had the most difficulty with correctly classifying individuals who make more than $50k/year due to class imbalance (4,945 in Class 0 and 1,568 in Class 1).
- Further analysis should implement additional feature engineering on the other categorical variables such as Occupation, Marital_status, and Working_class.
- Additional, further analysis may require implementing a more robust method for combating class imbalances to improve model accuracy.
