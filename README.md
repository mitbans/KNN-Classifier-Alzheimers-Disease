## Project: Distinguishing Alzheimer’s Disease Patients from Healthy Individuals

### Business Problem
The goal of this project is to accurately distinguish Alzheimer's disease patients from healthy individuals using handwriting data. Early and accurate detection of Alzheimer's disease is crucial for timely intervention and management.

### Data Collection
- **Dataset:** DARWIN dataset from UCI Machine Learning Repository
- **Repository URL:** [DARWIN Dataset](https://archive.ics.uci.edu/dataset/732/darwin)
- **Data URL:** [Download Data](https://archive.ics.uci.edu/static/public/732/data.csv)

#### Dataset Information
- **Participants:** 174
- **Features:** 450 (300 float64, 150 int64)
  - Features include measurements related to handwriting characteristics such as air time, total time, and various detailed time intervals for different tasks.
- **Target Variable:** `class`
  - `P` (Positive) - 89 instances (Alzheimer's patients)
  - `H` (Negative) - 85 instances (Healthy individuals)

### Data Preprocessing
- **Missing Values:** Checked, there are no missing values.
- **Standardization:** Standardized feature values to ensure uniformity and improve model performance.
- **Data Split:** Split the dataset into training (75%) and testing (25%) sets to evaluate model performance on unseen data.

### Model Development
#### Algorithm
- **Model:** K-Nearest Neighbors (KNN)
- **Hyperparameter Tuning:** Performed Grid Search Cross-Validation (Grid Search CV) to find the optimal K value.
- **Parameters Tested:** K values ranging from 1 to 129.
- **Optimal K:** 3 (determined based on Grid Search CV using accuracy).

#### Training Misclassification Rates
- **Evaluation:** Misclassification rates were evaluated for K values from 1 to 129.
- **Result:** Best K identified as 3, providing the lowest misclassification rate.

### Model Evaluation Metrics
- **Accuracy:** Used as the primary metric during initial Grid Search CV.
- **Precision, Recall, F1 Score:** Evaluated using the Precision-Recall Curve to determine the optimal threshold.
- **ROC AUC:** Used to confirm the model's discriminative ability.

#### Precision-Recall Curve
- **Optimal Threshold:** 0.33 (determined based on the Precision-Recall Curve).
- **Interpretation:** The Precision-Recall Curve indicated the best trade-off between precision and recall at this threshold.

#### ROC Curve
- **Best K:** 3 with an optimal threshold of 0.33 provided an AUC of 0.65.
- **Further Optimization:** Grid Search CV for K values ranging from 1 to 33 (step 2) with scoring based on ROC AUC identified K=11 as the optimal value.

### Conclusion
- **Optimal Metric:** Recall, Precision, and F1 Score.
- **Objective:** Maximize the detection of Alzheimer's patients (minimize false negatives).
- **Outcome:** Using the optimal K value of 3 and threshold of 0.33 provided the best balance between detecting true positives and minimizing false negatives.

#### Confusion Matrix
Confusion matrices were generated to visualize the performance of the model at various stages:
- **Initial Model (K=3, Threshold=0.33):** Provided insights into the classification performance.
- **Optimized Model (K=11 based on ROC AUC):** Showed less improved detection capabilities.

#### Screenshots
- **Training Misclassification Rates:**
<img width="1060" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/1e21a55e-7545-46c1-afa1-eb493bba18e1">
  
- **Model Output:**
<img width="396" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/8bc6be7f-0f42-414d-9456-755a4c7cb4f2">

- **Precision-Recall Curve:** 
<img width="541" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/23ab1a10-a6d9-43bc-81a2-79be10dba016">

- **ROC Curve:**
<img width="575" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/155988be-bab4-4802-8319-adc64e26f45a">
<img width="457" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/18de0671-4deb-4bdb-9fe6-0551c5aa88b6">

- **Confusion Matrices:** 
<img width="650" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/78ab294e-2f36-4b9e-abf5-66ec4476b46f">
<img width="637" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/8d24dafe-8f54-4c7f-8ffa-877eb83c53c9">
<img width="594" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/4668d491-bf34-4741-aae7-301e16fcb455">
<img width="533" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/a788a042-6a92-43d6-83f4-0e56b4f8df4c">

<div class="image-row">
  <div class="image-column">
    <img width="650" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/78ab294e-2f36-4b9e-abf5-66ec4476b46f">
  </div>
  <div class="image-column">
    <img width="637" alt="image" src="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/assets/166747739/8d24dafe-8f54-4c7f-8ffa-877eb83c53c9">
  </div>
</div>

### Further Analysis
- **Feature Importance:** Analysis to understand which handwriting features contribute most to distinguishing between Alzheimer's patients and healthy individuals.
- **Model Robustness:** Evaluated the model's robustness by testing on additional validation datasets, if available.

### References
- DARWIN Dataset: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/732/darwin)

### Repository Structure
- <code>notebooks/KNN-Classifier-Alzheimers-Disease.ipynb</code>: Jupyter notebook with code.
- <code>README.md</code>: Summary of findings and link to notebook

### Notebook
The detailed analysis and code can be found in the Jupyter notebook <a href="https://github.com/mitbans/KNN-Classifier-Alzheimers-Disease/blob/main/notebooks/KNN-Classifier-Alzheimers-Disease.ipynb">here</a>.
