# Deep Complex Separator

Deep Complex Separator (DCS) is a neural architecture designed for speech separation. This repository contains the code used in the paper "Deep Complex Separator" that is currently under review at ICLM 2019. We also illustrate the needed steps to replicate the results reported in the paper.

## The proposed architecture

## How to replicate our results

### Step 1 - Generate the Data
In our experiments we evaluated our system using the standard Wall Street Journal dataset (WSJ0) on two speaker mixtures.  To generate this dataset you have to follow these steps:
 - If not already available, you have to download the WSJ0 dataset from the [LDC website](https://catalog.ldc.upenn.edu/LDC93S6B).
-  Go to [this github repository](https://github.com/pchao6/LSTM_PIT_Speech_Separation/tree/master/2.%20create-speaker-mixtures-V2) and run the MATLAB script *create_wav_2_speakers.m*. Note that this script assumes that WSJ0's wv1 sphere files have already been converted to wav files, using the original folder structure under wsj0/. You can convert them using sox. Remember to set the variable wsj0root, output_dir16k, output_dir8k according to your paths.
- The scripts automatically creates some sub-folders (e.g., "8k", "16k"). In our study we used the data in "8k/min" subfolder, that correspons to a sampling frequency of 8 kHz.

### Step 2 - Train the Deep Complex Separator
You can start training our architecture by running the following command:

Note that we tested out code using PyTorch 1.0 and Python 3.7. 


### Step 3 - Evaluation
To evaluate the model on the test data, run the following command:

You should obtaine a Signal-to-Distortion-Ratio (SDR) of about 10.58 dB, which corresponds to the best performance reported in the paper,
