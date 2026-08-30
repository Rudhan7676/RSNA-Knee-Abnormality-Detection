# RSNA Knee Abnormality Detection

## Overview

This project implements a deep learning-based system for detecting abnormalities in knee MRI scans using a Convolutional Neural Network (CNN).

The project is based on the RSNA Knee Abnormality Detection competition dataset. It treats the task as a **multi-label classification problem**, where a single MRI study can contain multiple abnormalities at the same time.

The model predicts the probability of 12 different knee abnormalities and also provides a simple `Detected` / `Not Detected` result.

## Objectives

- Process knee MRI images stored in DICOM format.
- Select a representative MRI series for each study.
- Preprocess MRI images for deep learning.
- Prepare labels for multiple abnormalities.
- Train a CNN-based classification model.
- Validate the trained model.
- Generate predictions for test studies.
- Produce a competition submission file.
- Provide interpretable abnormality detection results.

## Dataset

The project uses the **RSNA Knee Abnormality Detection** dataset.

The dataset contains knee MRI studies, MRI series information, DICOM images, and abnormality labels.

The implementation uses:

- `train.csv`
- `train_series.csv`
- `test.csv`
- `test_series.csv`

The training data used during development contained:

- 4,407 training studies
- 24,371 training MRI series
- 12 abnormality categories

The test environment contained:

- 3 test studies
- 15 test MRI series

The original dataset is not included in this repository because of its large size and competition/data restrictions.

## Abnormalities

The model predicts the following 12 abnormalities:

1. ACL
2. MCL
3. Medial Meniscus
4. Lateral Meniscus
5. Medial OA
6. Lateral OA
7. PF OA
8. Effusion
9. Synovitis
10. Baker's
11. Contusion
12. Fracture

Where:

- ACL = Anterior Cruciate Ligament
- MCL = Medial Collateral Ligament
- OA = Osteoarthritis
- PF OA = Patellofemoral Osteoarthritis

## Methodology

The overall pipeline is:

```text
MRI Dataset
     ↓
Load Metadata
     ↓
Prepare Labels
     ↓
Select MRI Series
     ↓
Read DICOM Images
     ↓
Preprocess Images
     ↓
Train / Validation Split
     ↓
CNN Model
     ↓
Model Training
     ↓
Validation
     ↓
Best Model
     ↓
Test Prediction
     ↓
12 Abnormality Probabilities
     ↓
Detected / Not Detected
     ↓
Submission File
