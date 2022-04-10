# Neural Network Charity Analysis

## Overview
<p>In this analysis, using neural network machine learning, I attempted to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.</p>

## Results
<p>As part of data preprocessing I made the following determinations:</p>

* The EIN, and NAME fields were dropped, as they didn't provide any value as a target or feature.
* The IS_SUCESSFUL field will be our target.
* The rest of the fields will act as our features (APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT).

<p>After using get_dummies() and StandardScalar() to make the feature data more uniform we made several attempts to improve our training accuracy. All training was done using 100 epochs.</p>

* For the first training and evaluation, I chose to have double the number of features as my neurons (80), and 2 hidden layers. Both using the 'RELU' activation. This gave me about 73% accuracy.

&nbsp;&nbsp;&nbsp;<img src="/images/attempt1_settings.png" width="385" /><br/>
&nbsp;&nbsp;&nbsp;<img src="/images/attempt1_results.png" width="476" /><br/>

* Next, I decided to add a 3rd hidden layer, keeping the number of neurons at 80, and using 'RELU' as my activation. This again only achieved about 73% accuracy.

&nbsp;&nbsp;&nbsp;<img src="/images/attempt2_settings.png" width="385" /><br/>
&nbsp;&nbsp;&nbsp;<img src="/images/attempt2_results.png" width="476" /><br/>

* Finally, I decided to use PCA to reduce the number of features I was using for input. I settled on 20 features, which retained just over 75% of the data. I also reduced the number of neurons to 20 for each of the 3 layers. This again only achieved about 73% accuracy.

&nbsp;&nbsp;&nbsp;<img src="/images/attempt3_settings.png" width="385" /><br/>
&nbsp;&nbsp;&nbsp;<img src="/images/attempt3_results.png" width="476" /><br/>

<p>I was not able to achieve the goal of 75% accuracy with any of my optimization attempts. Although I did notice that using batch_size of 1 slighly increased my accuracy and with further optimization may have lead to reaching the goal. However, running batch_size of 1 with that many epochs takes a significant amount of time.</p>


## Summary
<p>Overall our machine learning was only able to achieve 73% accuracy in predicting if the applicants would be successful if funded. To further improve our accuracy we could make several adjustments. First, by updating the batch size to be smaller. By default batch size is 32. Reducing it would force our neural network to consider more of the data, instead of summarizing. Next, because our scaled data has some negative values, we may want to try using the TANH activation. Since RELU only outputs values from 0 and above, any negative outputs would be 0.</p>

<p>Alternatively, I would recommend using a RandomForest classifier (decision tree) as the method for predicting funding outcomes with this data. RandomForest generally has high accuracy. It is also less likely to over-fit the data because not all trees will see all features. Lastly, it is easier to interpret the outcomes, as you can see the importance placed on each feature.</p>
