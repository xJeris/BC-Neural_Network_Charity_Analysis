# Neural Network Charity Analysis

## Overview
The purpose is well defined.

## Results
<p>As part of data preprocessing we made the following determinations:</p>

* The EIN, and NAME fields were dropped, as they didn't provide any value as a target or feature.
* The IS_SUCESSFUL field will be our target.
* The rest of the fields will act as our features (APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT).

<p>After using get_dummies() and StandardScalar() to make the feature data more uniform we made several attempts to improve our training accuracy. All training was done using 100 epochs.</p>

* For the first training and evaluation, I chose to have double the number of features as my neurons (80), and 2 hidden layers. Both using the 'RELU' activation. This gave me about 73% accuracy.
* Next, I decided to add a 3rd hidden layer, keeping the number of neurons at 80, and using 'RELU' as my activation. This again only achieved about 73% accuracy.
* Finally, I decided to use PCA to reduce the number of features I was using for input. I settled on 20 features, which retained just over 75% of the data. I also reduced the number of neurons to 20 for each of the 3 layers. This again only achieved about 73% accuracy.

<p>I was not able to achieve the goal of 75% accuracy with any of my optimization attempts. Although I did notice that using batch_size of 1 slighly increased my accuracy and with further optimization may have lead to reaching the goal. However, running batch_size of 1 with that many epochs takes a significant amount of time.</p>


## Summary
The results are summarized, and there is a recommendation on using 
a different model to solve the classification problem, with a justification.
