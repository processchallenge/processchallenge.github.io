---
title: "Instructions"
permalink: "/instructions/"
mathjax: true
categories: media
layout: page
---
# Important Note
* The **intellectual property (IP)** is not transferred to the challenge organisers, i.e., if code is shared/submitted, the participants remain the owners of their code (when the code is made publicly available, an appropriate licence should be added).
* Participants can **submit up to 3 results** coming from **3 different models**, and the best model will be considered. Invited papers should introduce the models they attempt.
* **Test scores submission instruction**  
  * Step 1: Receiving and naming the file: 
  The shared test set directory includes a CSV file called "PROCESS_submission_<GROUP-NAME>_<AFFILIATION>.csv". Please replace <GROUP-NAME> with your group name and <AFFILIATION> with your affiliation that you registered with while sending us the scores from your models. 

  * Step 2: Populating the scores:
The CSV file contains columns which are Test_ID, Model1_class, Model2_class, Model3_class, Model1_MMSE, Model2_MMSE, Model3_MMSE. If you decide to submit the results for less than three models, please keep the corresponding column empty. Please double-check that your predicted classes correctly correspond to the test IDs. 

  * Step 3: Please make sure: 
No cell is kept empty for a column for which you are submitting results; otherwise, that column will be automatically ignored while calculating your scores.  The predicted class names must be the same as they appear on the training set, and they are "Dementia", "MCI" and "HC". 

  * Step 4: Submission: 
Please upload your RENAMED CSV file with your affiliation and group name to this [Google Form](https://forms.gle/869e6zcq3CaJS7uD8). Multiple submissions are permitted and the most recent CSV file will be considered for the scoring. Please make sure only one team member submits the test scores to avoid having unnecessary duplicates. 

# Tasks

1. **Classification**: This task is aimed at identifying those with different cognitive impairments and dementia from healthy volunteers through the processing of their speech.
2. **Regression**: This task is to predict the corresponding Mini Mental Status Examination (MMSE) score of speakers from their speech.

# Evaluation
## Classification task
The evaluation of the classification task will be done through standard classification and regression metrics. These metrics can be calculated globally by counting the total true positives, false negatives, and false positives:

* **Macro-Precision**: The averaged ratio of correctly predicted positive observations to the total predicted positives.
$$ \text{Macro-Precision} = \frac{1}{N} \times \sum_{i=1}^{N} \text{Precision}_i,   \text{Precision}_i = \frac{TP_i}{TP_i + FP_i} $$
* **Macro-Recall**: The averaged ratio of correctly predicted positive observations to all observations in the actual class
$$ \text{Macro-Recall} = \frac{1}{N} \times \sum_{i=1}^{N} \text{Recall}_i,  \text{Recall}_i = \frac{TP_i}{TP_i + FN_i} $$
* **Macro-F1 Score**: The Harmnic average of Precision and Recall.
$$ \text{Macro-F1 Score} = \frac{1}{N} \times \sum_{i=1}^{N} 2 \times \frac{\text{Precision}_{i} \times \text{Recall}_{i}}{\text{Precision}_{i} + \text{Recall}_{i}} $$

where $$N$$ is the number of diagnostic classes, $$TP{_i}$$, $$FP{_i}$$, $$FN{_i}$$ are true positives, false positives, and false negatives for the i-th class, respectively.

## Regression task
The evaluation of the regression task will be via the root mean squared error (RMSE):

$$ RMSE = \sqrt{\frac{\sum_{i=1}^N (\hat{y}_i - y_i)^2}{N}} $$

where $$y_i$$ is the actual MMSE score and $$\hat{y}_i$$ is the predicted MMSE score.

The ranking rules are divided into classification task ranking, regression task ranking, and a joint, combined ranking. The combined ranking evaluates performance across both tasks. The combined ranking criteria are:

$$ S_{k} = \frac{F1 Score_{k}}{\sum_{j}^{T} F1 Score_{j}} + 1 - \frac{\mathrm{RMSE}_{i}}{\sum_{j}^{T} \mathrm{RMSE}_{j}} $$

where $$S_{k}$$ is the total score of participant $$k$$ and $$T$$ is the total number of participants in the challenge. If a participant does not submit results for a task, the score for that task is set to 0. The following five participants will be invited to submit their papers:
* The top two participants with the highest F1 score in the classification task.
* The top two participants with the lowest RMSE in the regression task.
* The participant with the highest combined ranking score.

If a participant submits both classification and regression tasks and is invited for both, their invitation will be based on the higher ranking task. Participants invited for either the classification or regression tasks will not be considered for the joint ranking. This ranking criteria follows our sister challenge, the Multilingual Alzheimer's Dementia Recognition through Spontaneous Speech (ICASSP 2023) and is designed to encourage participants to engage in both tasks simultaneously as it increases their likelihood of receiving an invitation. 