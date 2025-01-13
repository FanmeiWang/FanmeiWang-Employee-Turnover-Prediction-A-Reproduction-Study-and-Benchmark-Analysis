# Predicting Employee Turnover: Scoping and Benchmarking the State-of-the-Art 

- **Fanmei Wang**:
  - Searched, selected, and reviewed the journal article **Predicting Employee Turnover: Scoping and Benchmarking the State-of-the-Art** from the journal **Business & Information Systems Engineering** for the project.
  - Cloned the GitHub repository (https://github.com/SimonDeVos/turnover_prediction) provided by the authors to reproduce the experiments.
  - Reproduced the Logistic Regression (LR) model on the IBM dataset using the configurations outlined in the paper.
  - Adapted and configured main.py for running experiments, including dataset selection, hyperparameter tuning, and model-specific settings.
  - Executed experiments and generated evaluation metrics to validate the paper's findings.
  - Set up the experimental environment by installing dependencies using the provided requirements.txt and ensuring compatibility with Python 3.12.7.

## Overview
This project reproduces experiments from the paper *Predicting Employee Turnover: Scoping and Benchmarking the State-of-the-Art* by De Vos et al. (2024). The study evaluates the performance of various classification models on employee turnover prediction, focusing on the IBM dataset and the Logistic Regression (LR) model in this reproduction.

## Objectives
- Validate the performance of the LR model on the IBM dataset.
- Examine model performance across various metrics like Accuracy, Precision, Recall, etc.

## Dataset
The dataset used for this project is the IBM dataset (public), including 1,470 records with 35 features, such as employee demographics, work-related factors, attrition status, etc. It is designed to help identify key factors influencing employee turnover.

## Steps Followed

**Step 1: Cloning**
- Accessed the GitHub repository provided by the authors and cloned it into the local environment. 
- After cloning, updated the path configurations to match with the local folder structure and ensure that the codes can be executed locally.

**Step 2: Configuration of the Dataset**
- Analyzed the dataset setup requirements and determined to use the IBM dataset as the data source for this reproduction task.
- The experiment configuration file was modified to enable only the Logistic Regression (LR) model, whereas the rest of the models were disabled.

**Step 3: Environment Setup**
- Created a virtual environment in Python locally and installed all required dependencies, such as NumPy, Pandas, and scikit-learn, by using the requirements.txt file.
- Checked the package versions installed to make sure that they meet the running requirements described.

**Step 4: Experiment Execution**
- Ran the main experiment script to retrieve the results, including but not limited to Accuracy, Precision, Recall, F1-Score, etc.
- The output was then saved in a text file.

**Step 5: Evaluation**
- The output metrics were documented and then compared against the results reported in the paper.  
- Checked whether my reproduction results were in line with the findings reported in the paper.

## Contributions Code
Following the author's instructions, I modified the dataset and methodology configurations in `main_FanmeiWang.py` to align with the paper's focus on the IBM dataset and the Logistic Regression model. Specifically:
1. In the `datasets` dictionary, `'ibm': True` was enabled to use the IBM dataset as the data source, while all other datasets were disabled.
2. In the `methodologies` dictionary, `'lr': True` was enabled to focus exclusively on the Logistic Regression model, while other classifiers were disabled.

## Results Summary
| Metric        | Reproduced Result | 
|---------------|-------------------|
| Accuracy      | 0.8388            | 
| Recall        | 0.0000            | 
| Precision     | 0.0000            | 
| F1-Score      | 0.0000            | 
| AUC-PR        | 0.3546            | 
| AUC-ROC       | 0.6430            | 
| H-Measure     | 0.0000            | 
| Brier Score   | 0.1334            | 

## Performance Comparison

The paper does NOT provide individual performance metrics for the LR model specifically on the IBM dataset. However, Table 5 shows us the average rankings of classifiers across datasets, providing insights into the general trends of various performance metrics. Even though these rankings are not specific to the IBM dataset, they still can be considered as a useful reference for us to understand the relative performance of the LR model.

Below is a comparison of my reproduced results with the general trends indicated in Table 5:

1. **Accuracy**:  
   My model achieved an accuracy of 0.8388, which reflects its strong performance in predicting the majority class. Table 5 shows that, on average, LR performs moderately well and stands at a ranking of 8.1. Thus, the reproduced result is in line with this trend.

2. **Recall, F1-Score, Precision, and Specificity**:  
   The reproduced results for all four metrics were 0.0000, which indicates that the model completely failed to predict any minority class instances in the IBM dataset. Table 5 shows the following rankings for these metrics across multiple datasets:  
   - Recall: Ranked 10.9, showing poor performance.  
   - F1-Score: Ranked 9.9, also showing poor performance.  
   - Precision: Ranked 8.0, showing moderate performance on average.  
   - Specificity: Ranked 7.1, showing moderate performance, slightly better than Recall and F1-Score.  
   However, the reproduced results on the IBM dataset indicate that the LR model entirely fails to handle the class imbalance effectively.

3. **AUC-PR**:  
   The model achieved an AUC-PR score of 0.3546, which shows moderate performance in balancing precision and recall across various thresholds. Table 5 ranks AUC-PR at 7.9, which indicates acceptable but not superior performance. The reproduced result is in line with the paper’s trend.

4. **AUC-ROC**:  
   The AUC-ROC score was 0.6430, which indicates its moderate ability to distinguish between the majority and minority classes. Table 5 ranks LR's AUC-ROC performance at 7.6, indicating that the model performs moderately well. The reproduced result is in line with the paper’s trend.

5. **H-Measure**:  
   The H-Measure score was 0.0000, implying that the model cannot manage class imbalance effectively. Table 5 ranks LR's H-Measure performance at 10.0, supporting the conclusion that class imbalance hinders the model’s performance.

6. **Brier Score**:  
   The Brier Score was 0.1334, suggesting reasonable calibration of predicted probabilities. Table 5 ranks Brier Score at 6.4, which shows moderate performance in calibration. The reproduced result aligns well with this finding.

## Limitations
- The reproduction was done only on the IBM dataset and the LR model, and results may differ if another dataset or algorithm were to be used. 
- The lack of balancing in the IBM dataset may have significantly affected the LR model’s performance metrics, particularly for minority class predictions, resulting in poor Recall, Precision, and F1-Score outcomes.

## Future Work
- I plan to extend my reproduction to include models like Random Forest and XGBoost, because they show better performance in handling imbalanced datasets.
- I will explore advanced balancing techniques (e.g., SMOTE, ADASYN) to improve performance on minority classes.
- I will apply deep learning approaches, such as BERT, for textual analysis of employee feedback and turnover prediction.

## Citation
De Vos, S., Bockel-Rickermann, C., Van Belle, J., & Verbeke, W. (2024). Predicting Employee Turnover: Scoping and Benchmarking the State-of-the-Art. *Business & Information Systems Engineering, 1–20.* Springer. [https://doi.org/10.1007/s12599-024-00898-z](https://doi.org/10.1007/s12599-024-00898-z)
