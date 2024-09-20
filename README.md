# Novartis-Server-Hack-Classification
The notebook primarily focuses on a **classification problem** related to predicting server hacks based on historical data. Here's a breakdown of the key aspects:

### Problem Statement:
The objective is to classify whether a server incident leads to multiple offenses (hacks) based on various features of the server logs. This is a binary classification problem, where the goal is to predict the likelihood of multiple offenses happening.

### Dataset Details:
- The dataset likely contains logs or details about server incidents with labeled outcomes for whether multiple offenses occurred or not. 
- Columns seem to include identifiers such as `INCIDENT_ID`, along with other feature columns used for prediction.
- The dataset is split into a training set (`X_train`, `y_train`) and a testing set (`X_test`), and the `MULTIPLE_OFFENSE` column is likely the target variable.

### Approach:
1. **Data Preprocessing:**
   - Data cleaning and feature engineering steps may include handling missing data, standardizing or scaling features, and converting categorical data if needed.
   - The data is likely standardized or normalized (scaling done with `X_train_sc` and `X_test_sc`).
   
2. **Model Selection:**
   Multiple machine learning models were trained and evaluated:
   - Support Vector Machine (SVM)
   - Random Forest
   - Decision Tree
   - Gradient Boosting Classifier (GBK)
   - k-Nearest Neighbors (k-NN)
   
   The performance of each model was measured based on **accuracy** and **recall** scores. The Gradient Boosting Classifier achieved the highest accuracy and recall (both around 99.69%).

3. **Final Model Selection:**
   After evaluating all models, the Gradient Boosting Classifier was chosen as the best-performing model.

Based on the notebook, I chose the **Gradient Boosting Classifier (GBK)** as the best-performing model. Here's why it was selected as the best:

### Model Evaluation Metrics:
Five models were trained and compared using **Accuracy** and **Recall** scores:

| Model                         | Accuracy Score | Recall Score |
| ------------------------------ | -------------- | ------------ |
| Gradient Boosting Classifier    | 99.69%         | 0.996641     |
| Decision Tree                   | 99.53%         | 0.996630     |
| Random Forest                   | 99.36%         | 0.994020     |
| k-Nearest Neighbors Classifier   | 95.28%         | 0.994294     |
| Support Vector Machine          | 95.21%         | 0.960274     |

### Why Gradient Boosting Classifier was Chosen:
1. **Highest Accuracy**: 
   - The Gradient Boosting Classifier had the highest accuracy (99.69%) among all the models, meaning it correctly predicted the most instances of whether multiple offenses occurred.
   
2. **High Recall**:
   - The recall score (0.996641) is also the highest, indicating that the model effectively identified actual positive cases (multiple offenses) with minimal false negatives. This is particularly important for classification tasks where identifying positive cases correctly (i.e., avoiding false negatives) is critical.

3. **Robustness**:
   - Gradient Boosting typically performs well with tabular data, handling complex decision boundaries better than simpler models like Decision Trees. It also minimizes overfitting due to its sequential nature, where each model in the ensemble corrects the errors made by the previous ones.

4. **Balance of Performance**:
   - While Decision Tree and Random Forest models also performed well, Gradient Boosting showed a slight edge in both accuracy and recall, making it a more reliable choice.

In summary, the **Gradient Boosting Classifier** was chosen due to its superior performance in terms of accuracy and recall, and its ability to handle the nuances of the dataset effectively.
