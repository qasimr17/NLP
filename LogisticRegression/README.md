# Logistic Regression From Scratch

This notebook contains code to implement a logistic regression model, using both stochastic and batch gradient descent for sentiment classification.



The dataset provided is part of the [Large Movie Review Dataset](https://ai.stanford.edu/~amaas/data/sentiment/) containing separate labelled train and test sets. 



## Dataset

The core dataset contains 50,000 movie reviews, split evenly into 25k train and 25k test sets each containing an even distribution of 12,500 positive and negative labelled reviews. 

For a more concise dataset, used in this repository, extract the required information from the public drive link [here](https://drive.google.com/drive/folders/1rz5KqIDZjgN4WYz6lymvxvfa6th4urWb?usp=sharing).

The directory structure for this dataset is as follows:

```bash
└───Dataset
    ├───test
    │   ├───neg
    │   └───pos
    └───train
        ├───neg
        └───pos
```

Reviews are stored in text files that are named according to the convention: `[[id]_[rating].text]` where `[id]` is the unique id of the review and `[rating]` is the rating given to the movie on a scale of 1-10. For example, the file `test/pos/200_8.txt` is the text for a positive-labeled test set example with unique id 200 and star rating 8/10 from IMDb.



## Data Preprocessing

Each review is represented by 6 features x<sub>1</sub>,...,x<sub>6</sub> according to the following table:

 

| **Feature**   | **Definition**                       | **Comment**                  |
| ------------- | ------------------------------------ | ---------------------------- |
| x<sub>1</sub> | count (positive words)  $\in$ review | Positive lexicon is provided |
| x<sub>2</sub> | count (negative words) $\in$ review  | Negative lexicon is provided |
| x<sub>3</sub> | Star Rating (1-10 scale)             | Mentioned in filename        |
| x<sub>4</sub> | log (word count of review)           |                              |
| x<sub>5</sub> | 1 if "no" $\in$ review, 0 otherwise  |                              |
| x<sub>6</sub> | 1 if "!" $ \in$ review, 0 otherwise  |                              |
| y             | 1 if positive, 0 otherwise           | Mentioned in directory name  |


