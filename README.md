# MindWatch2

Deep learning-based multimodal seizure prediction framework using EEG, ECG, EMG, and motion signals collected from wearable monitoring systems.

## Project Overview

This project proposes an end-to-end multimodal deep learning pipeline designed to improve seizure prediction performance by integrating multiple physiological modalities instead of relying only on EEG signals.

The framework combines:

* CNN-based spatial feature extraction
* BiLSTM temporal modeling
* Multimodal fusion
* Class imbalance handling strategies

The system predicts three states:

* Normal
* Preictal
* Ictal

## Methodology

The proposed pipeline consists of several stages:

### 1. Data Preprocessing

Signal preprocessing was applied to improve signal quality and maintain synchronization between modalities.

Processing steps include:

* Notch filtering
* Band-pass filtering
* Artifact reduction
* Windowing (4-second windows)

Additional modality-specific preprocessing was applied for EEG, ECG, EMG, and motion signals.

### 2. Class Imbalance Control

To improve minority-class learning and reduce bias toward normal samples, multiple imbalance control strategies were implemented:

* Excluding runs without EEG recordings
* Zero-padding missing modalities
* Excluding IMPD periods
* Limiting normal recordings
* Weighted Random Sampling (WRS)
* LDAM-DRW optimization

### 3. Deep Feature Extraction

Multimodal CNN architectures were used to automatically extract spatial features from physiological signals.

### 4. Temporal Modeling

BiLSTM networks were utilized to capture temporal dependencies and sequential seizure-related patterns.

### 5. Evaluation

The framework was evaluated using subject-independent validation strategies and multiple performance metrics.

## Repository Contents

* `PREPROCESS.IPYNB`
  Signal preprocessing pipeline.

* `HandCraft_AllModalities.IPYNB`
  Handcrafted feature extraction experiments.

* `CNN_AllModalities.IPYNB`
  Multimodal CNN experiments.

* `CNN_EEGonly.IPYNB`
  EEG-only CNN experiments.

* `BiLSTM*_Result`
  BiLSTM training and evaluation experiments using different configurations and imbalance strategies.

## Technologies Used

* Python
* PyTorch
* NumPy
* Pandas
* Scikit-learn
* MNE

## Notes

This repository contains implementation files, experimental notebooks, and project-related results for the proposed multimodal seizure prediction framework.
