# Reject-Inference-Project
## Objectives:

The project aims to develop a credit scorecard using data from all through-the-door credit customers. Among these customers, some have their credit applications rejected, resulting in a lack of information about their behavior at the time the scorecard is developed. Only the accepted clients have accumulated sufficient credit history, allowing us to label them as 'bad' or 'good' based on whether they have defaulted on their payments.

A straightforward approach to building a scorecard in this situation is to treat the rejects as Missing at Random (MAR) and to perform list-wise deletion of these cases. This means that the scorecard will be based solely on accepted applicants, who have a known good or bad status (referred to as the KGB sample). However, ignoring the rejected applications can introduce bias, as they usually represent a significant portion of the overall banking portfolio.

To address this issue, we can perform reject inference, which involves inferring the behavior of rejected applicants using the KGB model. Several techniques are available for this purpose, including Soft Augmentation, Fuzzy Augmentation, and Parcelling. The reader is encouraged to explore each of these methods. In this project, we will adopt the Simple Augmentation methodology.


This project delves into several important concepts and tools, including:  
- Automated explanatory data analysis utilizing Sweetviz.  
- Discretization of numerical features through OptBinning and subsequent transformation to the corresponding Weight of Evidence (WOE).  
- Determining the optimal threshold for flagging rejected samples.  
- Exploring a wide range of machine learning models to predict defaults.  
