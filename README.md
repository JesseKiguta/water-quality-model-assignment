# About
The project contains 2 notebooks that were individually worked on by Nina and Jesse to build a neural network-based classification model that would predict the potability of water.
The data set contains these features (ph	Hardness	Solids	Chloramines	Sulfate	Conductivity	Organic_carbon	Trihalomethanes	Turbidity).
We both used different optimization and regularization techniques in our models. 


# Summaries
## Nina
My model has an output layer, 3 hidden layers, and one output layer. 
Regularizer - L2 with a 0.001 learning rate
Optimizer - Adam with a 0.001 learning rate
dropout - 0.3 
Threshold of 0.6
Early stopping - patience 5 used to prevent overfitting
weight balance - 0:1, 1:5 to handle class imbalance
epochs 500 and batch size 32
My loss was 68.2% and val loss was 54.5%.
precision was 48.6% this was for the correct predicted positives.
the recall was 48.6% this shows how well my model captured the actual positives.
F1 was 59.6% which balances precision and recall.
Accuracy was 58.2% this was my overall correctness.
confusion matrix [[313 375][105 354]]

My model ultimately had many false positives and negatives according to the confusion matrix, indicating that the model was struggling to correctly both positive and negative classes. My F1 score also revealed that the model has a suboptimal balance between precision and recall.


## Jesse
The final performance metrics of my model and loss curves are as follows:
Training Accuracy: 70.49
Validation Accuracy: 66.61
Training Loss: 0.56
Validation Loss: 0.60

Apart from the final performance metrics, this is how my model performed on metrics such as the F1 Score:
Precision: 0.58
Recall: 0.66
F1 Score: 0.62

The following combination of techniques achieved the result above:
Optimizer: Nadam (with a learning rate of 0.0004)
Regularizers: Dropout (with a rate of 0.3) and Batch Normalization
Early Stopping (with a patience of 15)
ReduceLROnPlateau (with a factor of 0.3, patience of 7, and minimum learning rate of 1e-6)

The model shows mild overfitting as the training accuracy and loss are higher than the validation accuracy and loss by around 4 points. The precision score of 0.58 indicated that the model has a relatively high number of false positives with recall being a bit higher at 0.66 showing that the model is better trained for actual positives.


# Insights & Challenges
## Nina
My biggest challenge was with the class imbalance, getting the model to not favor the class with the highest amount of data required a lot of adjusting.
Working with class weights was very interesting getting the right ratio took a lot of time. My model was penalizing the majority class more.
Another challenge was getting a learning rate that would work well with the threshold and the class weights to produce a model that would converge and give better scores. I think working without the L@ would have helped the model converge faster and this is something I picked up on later. My overall insight is to always  try different optimizers and regularisers to see which one would help the model perform better.




## Jesse
To achieve these results, I carefully selected and finetuned different techniques. Because the model was initially converging too slowly leading to poor overall performance, I switched from Adam to Nadam, which helped the model converge faster and improve performance. In addition, I chose a combination of Dropout and Batch Normalization for regularization to reduce overfitting as much as possible, which made me arrive at an optimal dropout rate of 0.3. Furthermore, I used Early Stopping with a high patience of 15 because I observed that I was initially stopping the model too early which was not allowing room for improvement, and ReduceLROnPlateau to aid Nadam in converging the model in a better way.


# Summary Table
| Train Instance | Engineer Name | Regularizer | Optimizer | Early Stopping | Dropout Rate | Accuracy | F1 Score | Recall | Precision |
|---------------|--------------|-------------|-----------|---------------|-------------|----------|---------|--------|----------|
|2797               |Jesse Kiguta              |Dropout             |Nadam           |Yes               |0.3             |65.9          |61.7         |65.9        |58.0          |
|    982           |   Nina Mwangi           |    L2         |     Adam      |      yes         |  0.3           |    58.2      |  59.6       |    48.6    |     48.6     |

