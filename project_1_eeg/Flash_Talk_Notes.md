# Flash Talk Notes Project 1

## Group 17
- That's us :)

## Group 18
- [Data Augmentation for Deep Learning-based EEG](https://www.sciencedirect.com/science/article/pii/S0165027020303083)

## Group 19
- [Classification of EEG signals using Transformer based deep learning and ensemble models](https://www.sciencedirect.com/science/article/pii/S1746809423005633)
  - Not part of their presentation, but coincidentally encountered: [Efficacy of transformer networks for classification of EEG data](https://www.sciencedirect.com/science/article/pii/S1746809423009217)

## Group 20
- [Implementation of Convolutional Neural Network with EfficientNet-B0 Architecture for Brain Tumor Classification](https://ieeexplore.ieee.org/abstract/document/10381979)
- Imbalance in number of votes per EEG
- Weigh the number of votes during training

## Group 21
- Look for ensemble baselines that are diverse with good scores
- [Magic Formula to Convert EEG to Spectrograms!](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/discussion/469760)

## Group 22
- 8.7% of spectrograms have missing data and 4.8% of raw EEG files have missing data
- 7.25% of sub-EEGs in *train.csv* are linked to spectrograms with missing values, meaning that 7.25% of the data in the training set is missing.
- There is in imbalance in the labels: there are many spectrograms labeled as "Other".

## Group 23
- [Performance evaluation of EMD, DWT, and WPD for automated epileptic seizure detection and prediction](https://www.sciencedirect.com/science/article/pii/S1746809417301544)
  - 4 different machine learning methods: ANN, k-NN, SVM, RF
  - 3 different feature extraction methods: EMD, DWT, WPD
- [Classification of epileptic EEG recordings using signal transforms and convolutional neural networks](https://www.sciencedirect.com/science/article/pii/S0010482519301398)
- Use KerasCV baseline (pinned)
- Feature engineering on the spectrogram
- Planning on extracting WPD features from data and learn a k-NN to the data

## Group 24
- Functional Magnetic Resonance Imaging (FMRI) measures brain activity during activities to provide insights into cognitive function
- Inference in neuroimaging is the process that helps deduce which part of the brain is active for a given cognitive process
- Reverse inference is the opposite of inference, being a process which helps deduce cognitive processes from brain activity

## Group 25
- Feature extraction
  - Time domain features (Features extracted from the time dimension)
    - Mean value
    - Variance
    - Skewness
  - Frequency domain features (Features extracted from the wave frequency dimension)
    - Delta band frequency
    - Theta band frequency
    - Alpha band frequency
    - Beta band frequency
  - Correlation features
    - Cross-correlation
    - Autocorrelation
- Approaches
  - LSTM
  - Gradient-Boosted Decision Trees
  - CNN Features with Shallow Classifiers
  - Ensembles of these
- Kaggle discussions
  - [Understanding Competition Data and EfficientNetB2 Starter - LB 0.43 🎉](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/discussion/468010)
  - [🌩️HMS - EDA and Domain Journey🌍](https://www.kaggle.com/code/mvvppp/hms-eda-and-domain-journey)

## Group 26
- Current
  - Baseline models: ResNet34 and ViT (Vision Transformers)
    - Finetune on spectrograms
  - Possibly a better CNN-based model: YOLO, but we're not sure
- Planning
  - Multimodal learning approach: timeseries data model + spectrogram data model.
  - WaveNet as timeseries data model + EfficientNet as spectrogram data model

## Group 27 & 28
- Vanished into the aether

## Group 29
- Train (finetune?) a transformer since the data is sequential

## Group 30
- Train VAE to generate new spectrogram images to train on
- Spectrograms are fed to CNN-based models (ResNet & EfficientNet) and Transformer-based models (Vision Transformer)
- Vector representations of spectrograms directly fed to linear layer
- Take average prediction for every predictor, then ensemble the averages.
- Do you own spectrograms! Never trust data collection done by medical personnel, do your own data collection.
- Literature
  -  [Development of Expert-Level Classification of Seizures and Rhythmic and Periodic Patterns During EEG Interpretation](https://pubmed.ncbi.nlm.nih.gov/36878708/)
  - [SPaRCNet data: Seizures, Rhythmic and Periodic Patterns in ICU Electroencephalography](https://bdsp.io/content/bdsp-sparcnet/1.1/)
  - [Data augmentation for deep-learning-based electroencephalography](https://www.sciencedirect.com/science/article/pii/S0165027020303083)

## Group 31
- Wavelet transform: filtering seizure-relevant EEG signals from background noise
- Feature extraction:
  - Statistical features (e.g. mean)
  - Hjorth parameters
- Dragonfly Algorithm, a swarm intelligence feature selection algorithm.
- Wavelets --> dragonfly algorithm --> DNN
- CNN or WaveNet approach for spectrograms
- Make an ensemble out of these
- [EEG-based epileptic seizure detection using binary dragonfly algorithm and deep neural network](https://www.nature.com/articles/s41598-023-44318-w)
- [PyWavelets - Wavelet Transforms in Python](https://pywavelets.readthedocs.io/en/latest/)

## Group 33
- For a single EEG, multiple experts assign a label. This means that some EEGs have many, varying labels.
- Shit in is shit out
- Cool ice dragon ❄️🐉❄️
- Approach
  1. Change architectures (ResNet34d, WaveNet, 1d-2d CNN)
  2. Pre-built models (ResNet34d --> 26d)
  3. Filtering frequencies (0.5 Hz - 45 Hz)
  4. If scores improve, combine models into an ensemble
- Kaggle discussion: [Papers & Model Architectures](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/discussion/468771)

## Group 35
- ~70% of modern-day EEG classifications use CNNs
- Data Augmentation
  - Stretching the spectrograms
  - Masking frequency bands up to 20Hz
  - Masking time segments up to 50s
- Merging two networks
  - Run two separate networks: one for the EEG raw signals and one for the spectrograms
  - Merge the predictions prior to classification (ensemble)

## Group 36
- Also vanished into the aether

## Group 37
- From literature review, SVMs are commonly used
- We will use SVMs for EEG data and CNNs for spectrogram data
- Considered approaches: SVM, k-NN, LDA, CNN
- [Machine learning techniques for electroencephalogram based brain-computer interface: A systematic literature review](https://www.sciencedirect.com/science/article/pii/S2665917423001599)
