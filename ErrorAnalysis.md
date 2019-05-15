**Francis Donoso** **& ** **Massimo Vicenzo**

**Introduction to Computer Programming 360-420: Section 01**

**Report: Error Analysis**

**Distributions of Model Accuracy**

When k = 3, through 1000 iterations:

- We received an accuracy of 96.93% with a standard deviation of 1.02

Each time you run the classification model, you should be getting a different accuracy. Why?

- The reason we get a new accuracy every time is because Collections.shuffle(fulldataset) in the DataSet code reorganizes all the elements in the list so that they are randomly assigned to new places. So, when we are taking the values of our test set, it takes randomly assigned data each time it goes through the for loop of our main code kNNMain.

**Baseline comparison**

A sensible baseline to compare our model is by seeing which label is the most frequent in a set just classifying each element in that set by that label. If a label makes up 66% of the set then we should identify each element of that set as that label.

This baseline gives an accuracy of about 65%, which is much less accurate than our Nearest Neighbor model that has a accuracy of 96.93% and a standard deviation of 1.02.

**Analysis of different error types**

What is a false positive? It is when we predict something to be positive, when in reality it is negative. For example, when doctors say that you are sick when really you aren't sick.

What is a false negative? It is when we predict something to be negative, when in reality it is positive. For example, when doctors say that you aren't sick when you are sick.

**Precision vs. Recall**

When k = 3, through 1000 iterations:

- We received an average precision of 95.43% with a standard deviation of 4.95

- We received an average recall of 95.81% with a standard deviation of 6.33

  Precision: Precision is the accuracy of what we predicted. If we predicted 100 people were sick but only 99 were sick then our precision is 99%.

  Recall: Recall is how many relevant results we return versus how many relevant results there were. If we predicted that 100 people were sick and all 100 were sick then our precision is 100%, but if there were 20 extra people that we didn't even classify, then our recall is only 83.3%.

**Baseline comparison**

For precision our baseline comparison would be... 

​	Precision = (true positives)/ (true positives + false positives)

For recall our baseline comparison would be...

​	Recall = (true positives) / (true positives + false negatives)

**The Parameter K**

| k    | precision | recall |
| ---- | --------- | ------ |
| 1    | 94.75     | 93.16  |
| 3    | 95.44     | 95.77  |
| 5    | 95.58     | 95.59  |
| 7    | 95.73     | 94.99  |
| 9    | 95.92     | 94.35  |
| 11   | 96.12     | 93.81  |
| 13   | 96.16     | 93.14  |
| 15   | 96.37     | 92.70  |
| 17   | 96.40     | 92.25  |
| 19   | 96.46     | 91.98  |

As the parameter k increases...

- The precision increases
- The recall Decreases

When we do cases like breast cancer we want a higher recall because we would never want to give somebody with breast cancer a false negative. Being less precise in these scenarios is better because telling someone who doesn't have cancer that they do isn't the end of the world, but telling someone they don't when they do could be the end of the world for that person.