---
title: "Instructions"
permalink: "/instructions/"
layout: page
---

#### Tasks

1. **Classification**: This task is aimed at identifying those with different cognitive impairments and dementia from healthy volunteers through the processing of their speech.
2. **Regression**: This task is to predict the corresponding Mini Mental Status Examination (MMSE) score of speakers from their speech.

#### Evaluation
##### Classification task
The evaluation of the classification task will be done through standard classification and regression metrics. These metrics can be calculated globally by counting the total true positives, false negatives, and false positives:

* **Macro-Precision**: The averaged ratio of correctly predicted positive observations to the total predicted positives.
$$ Precision = \frac{1}{N} \times \frac{TP{_i}}{TP{_i} + FP{_i}} $$


* **Macro-Recall**: The averaged ratio of correctly predicted positive observations to all observations in the actual class

* **Macro-F1 Score**: The average of Precision and Recall.

where 
N
N is the number of diagnostic classes, 
T
P
i
TP 
i
​
 , 
F
P
i
FP 
i
​
 , and 
F
N
i
FN 
i
​
  are true positives, false positives, and false negatives for the 
i
i-th class, respectively.

##### Regression task
The evaluation of the regression task will be via the root mean squared error (RMSE):

where 
y
i
y 
i
​
  is the actual MMSE score and 
y
^
i
y
^
​
  
i
​
  is the predicted MMSE score.

The ranking rules are divided into classification task ranking, regression task ranking, and a joint, combined ranking. The combined ranking evaluates performance across both tasks. The combined ranking criteria are:

where 
S
k
S 
k
​
  is the total score of participant 
k
k and 
T
T is the total number of participants in the challenge. If a participant does not submit results for a task, the score for that task is set to 0. The following five participants will be invited to submit their papers:
* The top two participants with the highest F1 score in the classification task.
* The top two participants with the lowest RMSE in the regression task.
* The participant with the highest combined ranking score.

If a participant submits both classification and regression tasks and is invited for both, their invitation will be based on the higher ranking task. Participants invited for either the classification or regression tasks will not be considered for the joint ranking. This ranking criteria follows our sister challenge, the ICASSP 2023 and is designed to encourage participants to engage in both tasks simultaneously as it increases their likelihood of receiving an invitation.