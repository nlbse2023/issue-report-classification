# NLBSE'23 Tool Competition on Issue Classification

## Introduction

This NLBSE tool competition is on automatic issue report classification, an important task in issue management and prioritization.

For the competition, we provide a dataset encompassing more than TODO 800k labeled issue reports (as bugs, features, questions and documentation) extracted from real open-source projects. You are invited to leverage this dataset for evaluating your classification approaches and compare the achieved results against a two proposed baseline approaches based on FastText and RoBERTA.

## Participation

If you want to participate, you must:

- Train and tune a multiclass classifier using the provided training set. The classifier should assign one label to an issue.
- Evaluate your classifier on the provided test set
- Write a paper (4 pages max.) describing:
  - The architecture and details of the classifier
  - The procedure used to pre-process the data
  - The procedure used to tune the classifier on the training set
  - The results of your classifier on the test set
  - Additional info: provide a link to your code/tool with proper documentation on how to run it
- Submit the paper by the deadline (see below). Email the paper to the tool competition organizers: Rafael Kallis (rk@rafaelkallis.com) and Maliheh Izadi (m.izadi@tudelft.nl)

All submissions must conform to the ICSE’23 formatting and submission instructions.

Papers do not need to be double-blinded.

## Important Dates
  
- Paper/tool submission: TBA 2023
- Acceptance and competition results notification: TBA 2023
- Camera-ready paper submission: TBA 2023

All dates are anywhere on earth (AoE).

## Submission acceptance and competition

Submissions will be evaluated and accepted based on correctness and reproducibility, defined by the following criteria:

- Clarity and detail of the paper content
- Availability of the code/tool, including the training/tuning/evaluation pipeline, released as open-source
- Correct training/tuning/evaluation of your code/tool on the provided data
- Report the metrics and results we outline below
- Clarity of the code documentation

The accepted submissions will be published at the workshop proceedings.

The submissions will be ranked based on the F1 score (defined below) achieved by the proposed classifiers on the test set, as indicated in the papers.

The submission with the highest F1 score will be the winner of the competition.

## Referencing

Since you will be using our dataset (and possibly one of our notebooks) as well as the original work behind the dataset, please cite the following references in your paper:

```
@inproceedings{nlbse-issue-class2023,
  author={Kallis, Rafael and Izadi, Maliheh and Di Sorbo, Andrea and Panichella, Sebastiano},
  title={NLBSE'23 Tool Competition on Issue Classification},
  booktitle={Proceedings of The 2nd International Workshop on Natural Language-based Software Engineering (NLBSE'23)},
  year={2023}
}
```

## Training

## Evaluation

Submissions are evaluated based on their class-detection performance over the provided test set. The classifier should assign one label to an issue.

### Evaluation 

> Note: for correct latex rendering, open this notebook in Collab.

Submissions are evaluated based on their class-detection performance over the provided [test set](https://tickettagger.blob.core.windows.net/datasets/github-labels-top3-803k-test.tar.gz). 
The classifier should assign one label to an issue.

The distribution of (80,518) issues in the test set:
* bug:	40,152	(49.9%)
* enhancement:	33,290	(41.3%)
* question:	7,076	(8.8%)

The evaluation must be performed on the entire test set only. **Important:** you may apply any preprocessing or feature engineering on this dataset except sampling, rebalancing, undersampling or oversampling techniques.

Classification performance is measured using the $F_1$ score over all the three classes. 

A submission (i.e., paper) in the tool competition must provide:
- Precision, for each class and the micro average
- Recall, for each class and the micro average
- F1 score, for each class and the micro average

Micro-averaging was chosen as the cross-class aggregation method due to the class imbalance present in the data.

Please note that whilst all of the above measures must be provided for acceptance, the submissions will **only** be ranked by their F1 score.

## Templates

## Submission Template 1: FastText

Participants are encouraged, but not required, to use one of our templates for their submission. Each template downloads the dataset, performs basic preprocessing, trains a classifier and evaluates it on the evaluation set.

- [FastText]()
- [RoBERTA]()
