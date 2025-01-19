# Reject-Inference-Project
## Objectives:

The project aims to develop a credit scorecard using data from all through-the-door credit customers. Among these customers, some have their credit applications rejected, resulting in a lack of information about their behavior at the time the scorecard is developed. Only the accepted clients have accumulated sufficient credit history, allowing us to label them as 'bad' or 'good' based on whether they have defaulted on their payments.

A straightforward approach to building a scorecard in this situation is to treat the rejects as Missing at Random (MAR) and to perform list-wise deletion of these cases. This means that the scorecard will be based solely on accepted applicants, who have a known good or bad status (referred to as the KGB sample). However, ignoring the rejected applications can introduce bias, as they usually represent a significant portion of the overall banking portfolio.

To address this issue, we can perform reject inference, which involves inferring the behavior of rejected applicants using the KGB model. Several techniques are available for this purpose, including Simple Augmentation, Fuzzy Augmentation, and Parcelling. The reader is encouraged to explore each of these methods. In this project, we will adopt the Simple Augmentation methodology.


This project delves into several important concepts and tools, including:  
- Automated explanatory data analysis utilizing Sweetviz.  
- Discretization of numerical features through OptBinning and subsequent transformation to the corresponding Weight of Evidence (WOE).  
- Determining the optimal threshold for flagging rejected samples.  
- Exploring a wide range of machine learning models to predict defaults.

## Conclusion and recommendations:

In the end-to-end reject inference project, we applied the Simple Augmentation method, also known as the Hard Cut-off method. We trained a suite of machine learning models using known good and bad samples (KGB), ultimately identifying the extreme gradient boosting (XGB) model as the best performer, with an ROC AUC of 0.827 and a Gini coefficient of 0.654.

We determined an optimal threshold based on the highest F1 score and classified rejected customers as 'bad' or 'good' based on their default probability relative to this threshold. The rejected sample was combined with the KGB training sample to create a through-the-door dataset for further model training and evaluation.

The XGB model again proved to be the best, achieving ROC AUC and Gini scores of 0.810 and 0.619, respectively—only slightly different from the performance of the KGB model. Notably, the through-the-door model showed improved coverage of defaults, with a recall score of 0.884 compared to 0.811 for the KGB model. Further work includes exploring other reject inference methodologies such as Fuzzy Augmentation and Parcelling.
