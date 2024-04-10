# MLiP Project 1: HMS - Harmful Brain Activity Classification

The first project of the Machine Learning in Practice 2023 - 2024 course was **HMS - Harmful Brain Activity Classification**.
The goal of this Kaggle competition was to develop a model capable of recognizing and classifying varying types of harmful brain activity, including seizures.
The hosts of the competition provided competitors with a dataset of electroencephalography (EEG) signals which were manually labeled by multiple professionals into one of five harmful brain activity categories and a sixth ”other”-category. 
A model must then, given an EEG signal, predict the likelihoods of the signal belonging to any of the six categories.

For our solution, we built upon an existing solution provided by Andreas Bisi, which consisted of a notebook for [training](https://www.kaggle.com/code/andreasbis/hms-train-efficientnetb1) and a notebook for [inference](https://www.kaggle.com/code/andreasbis/hms-inference-lb-0-41).
As a team of three, we each worked on a different component of our final solution. 
We developed three different notebooks for training a model in different ways, and a collective inference notebook for submitting to the competition.
Further details may be found in our [report](/project_1/report.pdf).

## Training: Spectrograms
[Notebook](/project_1/code/train_spectrograms.ipynb)

Naomi Deenen experimented with different data preparation techniques to improve the model.
Specifically, she found that Andreas Bisi's solution applied normalization only on an instance level, normalizing EEG spectrograms only by their own means and standard deviation.
Naomi refined this process by applying a datawide normalization strategy, where all spectrograms are normalized using the mean and standard deviation of all EEG spectrograms in the dataset.

## Training: Meta-Learning
[Notebook](/project_1/code/train_meta_learning.ipynb)

Marieke van Vreeswijk experimented with meta-learning strategies.
Our baseline used an ensemble of multiple resource-intensive deep learning models.
Marieke experimented with training a simpler model that learns to copy the ensemble's behavior, in order to produce a model that is just as good as the ensemble, but much less computationally expensive.

## Training: Hyperparameters
[Notebook](/project_1/code/train_hyperparameters.ipynb)

I experimented with optimizing the hyperparameters of the models in the baseline ensemble.
I used the Optuna framework for this process and iteratively reduced the search space for optimal model results.

## Inference
[Notebook](/project_1/code/inference.ipynb)

The notebook can also be found [at Kaggle](https://www.kaggle.com/code/naomideenen/inference/notebook).

For our best solution, we used an ensemble of three models: an EfficientNetB0 model taken directly from Andreas' baseline, an EfficientNetB1 model with optimized hyperparameters, and an EfficientNetB1 model trained on spectrograms with the datawide normalization strategy.