# Reeve-Case-Study2

## Project Title
AI-Driven Detection and Grading of Knee Osteoarthritis in Radiographic Data

## Objective
To develop a deep learning–based system for automated detection and KL grading of knee osteoarthritis using X-ray images.

## Dataset
- Name: Knee Osteoarthritis Dataset with Severity Grading

- Source: Kaggle (author: shashwatwork / Shashwat Tiwari)


## Methodology
- Transfer learning using CNN architectures (ResNet, DenseNet)
- Data augmentation and preprocessing
- Evaluation using accuracy, precision, recall, and F1-score
- Model interpretability using Grad-CAM

## Current Status
Phase 1 Complete 

Current Progress (Phase 2)

- Dataset downloaded and verified locally (train/val/test splits, KL 0–4 labels).

- EDA completed: class distribution analysis + visual inspection across KL grades.

- Baseline transfer learning model implemented (ResNet-18 pretrained on ImageNet).

- Initial training completed (5 epochs) with evaluation on validation and test sets.

- Baseline Results (ResNet-18, 5 epochs)

     Test Accuracy: 0.598

     Test Macro F1: 0.629

Notes

- Strong class imbalance observed (KL 4 minority class).

- Most confusion occurs between adjacent KL grades (e.g., KL1–KL2, KL3–KL4), consistent with subtle radiographic differences.

Reproducibility

- Dataset is not stored in this repository due to size/licensing.

- Expected local path:
  data/raw/knee-osteoarthritis-dataset-with-severity/{train,val,test}
