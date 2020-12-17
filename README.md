## DataCamp
# Dreem
Dreem is a french neurotechnology startup which works on the Dreem headband, a tool for sleep analysis and enhancement to help people improve their sleep. The Dreem headband collects physiological activity during sleep, such as brain activity (EEG), respiration and heart rate. Physiological signals are analyzed throughout the night and allows to perform a detailed analysis of sleep. Sound stimulation is also provided to enhance sleep quality at different steps of the night : falling asleep, deep sleep and awakening.

# Predicting sex from EEG data
We propose reproducing the results of the following publication:

https://www.nature.com/articles/s41598-018-21495-7.pdf.

Abstract: “We have excellent skills to extract sex from visual assessment of human faces, but assessing sex from human brain rhythms seems impossible. Using deep convolutional neural networks, with unique potential to find subtle differences in apparent similar patterns, we explore if brain rhythms from either sex contain sex specific information. Here we show, in a ground truth scenario, that a deep neural net can predict sex from scalp electroencephalograms with an accuracy of >80% (p < 10−5), revealing that brain rhythms are sex specific.”

Dreem has a huge database composed of 1 000 000 of full night EEG recordings. We reproduced a dataset of good quality EEG signal to allow reproducing the described results. The main difference is the number of EEG channels used (7 vs 24 in the paper) but this is compensated by the face that 1) EEG channels are highly correlated in EEG recordings 2) we gathered more subjects than in the original study.

# Challenge goals
In this dataset, we try to predict the gender of someone based on 40 windows of 2 seconds taken during sleep.

# Dataset
Each sample represents 40 independant segments of 2 seconds of 7 EEG channels samples at 250 Hz.

The training matrix has shape: N_train x 40 x 7 x 500 The testing matrix has shape: N_test x 40 x 7 x 500

## Labels
The prediction is a label in {0, 1}, 0 stands for male and 1 for female.

## Data format
File format uses HDF5 format. To open it see: 

Python: http://docs.h5py.org/en/stable/quick.html
R: https://www.neonscience.org/hdf5-intro-r
