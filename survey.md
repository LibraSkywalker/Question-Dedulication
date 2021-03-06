﻿# A brief survey for question deduplication

There're two popular dataset for question deduplication which I will mention in the content below.

First, we should be clear that how these datasets can test performance of our model.

## Benchmark

### Accuracy
**NOTE:** The first dataset provides pairwised questions in order to detect duplication. 

The original dataset should be used to test the accuracy of our end model(which is model "supervised alpha")

### Efficiency
To test the efficiency of our framework, we should reorganize the dataset and mix all the questions and form a pool. Our whole framework should be compared to the predictor of other state-of-art algorithm with some basic thread-level parallelism.

## Datasets

### Quora Question Pairs (recommended)
Currently, Quora uses a Random Forest model to identify duplicate questions. In [Quora Question Pairs](https://www.kaggle.com/c/quora-question-pairs/data) competition, Kagglers are challenged to tackle this natural language processing problem by applying advanced techniques to classify whether question pairs are duplicates or not. Doing so will make it easier to find high quality answers to questions resulting in an improved experience for Quora writers, seekers, and readers.

**NOTE:** This dataset only uses the **title** of questions to detect duplicated question pairs.

##### implementation:

[YesOfCourse](https://github.com/HouJP/kaggle-quora-question-pairs) ranked 4/3396 in the Kaggle Quora Question Pairs Challenge.

[bradleypallen](https://github.com/bradleypallen/keras-quora-question-pairs) contains several solutions which performs well in the Kaggle Quora Question Pairs Challenge.

### Stackoverflow

This datasets contains the normal questions in Stackoverflow and some **EXACT DUPLICATE QUESTIONS**. 

 [Dataset](https://drive.google.com/file/d/0BweYiPG4aspAd0lMOElBdW9md2M/view)

**NOTE:** This dataset is in the **pickle** format, it should be load by pickle library in python.

##### implementation:

[DuplicationDetectionStackOverflow](https://github.com/lumig242/DuplicationDetectionStackOverflow) An implementation of paper [Multi-Factor Duplicate Question Detection in Stack Overflow](https://soarsmu.github.io/papers/jcst-duplicateqns.pdf)

[DupPredictorRep](https://github.com/muldon/dupPredictorRep) : implementation of [Duplicate Question Detection in Stack Overﬂow: A Reproducibility Study](http://lascam.facom.ufu.br/cms/userfiles/downloads/2017/saner18rene-preprint.pdf)

[DupeRep](https://github.com/muldon/dupeRep) : implementation of [Duplicate Question Detection in Stack Overﬂow: A Reproducibility Study](http://lascam.facom.ufu.br/cms/userfiles/downloads/2017/saner18rene-preprint.pdf)

## Similar ideas

I found some ideas that are similar to ours. I've listed below and let's think about what's the key difference.

[Duplicate Detection in Programming Question Answering Communities](http://users.ox.ac.uk/~coml0694/papers/toit17_wj.pdf)

## TODO

+ try to evaluate algorithms above.

+ find more contents related.
