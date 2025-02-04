# About
The project contains 2 notebooks thate were individually worked on by Nina and Jesse to build a neural network based classification model that would predivt the potability of water.
The data set contains these features (ph	Hardness	Solids	Chloramines	Sulfate	Conductivity	Organic_carbon	Trihalomethanes	Turbidity).
We both used different optimization and regularization techniques in our models. 


# Summaries
## Nina
My model has an output layer, 3 hidden layers and one out put layer. 
Regularizer - L2 with a 0.001 learning rate
Optimiser - Adam with a 0.001 learning rate
dropout - 0.3 
Threshold of 0.6
Early stopping - patience 5 used to prevent overfitting
weight balance - 0:1, 1:5 to handle class imbalance
epochs 700 and batch size 32
My loss was 68.2% and val loss was 54.5%.
precision was 48.6% this was for the correct predicted poistives.
recall was 48.6% this show how well my model captured the actual positives.
F1 was 59.6% this balances precision and recall.
Accuracy was 58.2% this was my overall correctness.
confusion matrix [[313 375][105 354]]
My model in the end had a high number of false positives accoriding to the confusion matrix.


## Jesse




# Insights & Challenges
## Nina
My biggest challenge was with the class imbalance, getting the model to not favor the class with the higest amount of data required alot of adjusting.
Working with class weights was very interesting getting the right ratio took alot of time. My model was penalizing the majority class more.
Another challenge was getting a learning rate that would work well with the threshold and the class weights to produce a model that would converge and give scores that are under 50%.




## Jesse



# Summary Table
| Train Instance | Engineer Name | Regularizer | Optimizer | Early Stopping | Dropout Rate | Accuracy | F1 Score | Recall | Precision |
|---------------|--------------|-------------|-----------|---------------|-------------|----------|---------|--------|----------|
|2797               |Jesse Kiguta              |Dropout             |Nadam           |Yes               |0.3             |65.9          |61.7         |65.9        |58.0          |
|    1082           |   Nina Mwangi           |    L2         |     Adam      |      yes         |  0.3           |    58.2      |  59.6       |    48.6    |     48.6     |

