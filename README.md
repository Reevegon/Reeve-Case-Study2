# Reeve-Case-Study2

## Project Title  
AI-Driven Detection and Grading of Knee Osteoarthritis in Radiographic Data

---

## Objective  
To develop a deep learning–based system for automated detection and KL grading (KL 0–4) of knee osteoarthritis using X-ray images.  

The project follows a research-driven workflow including:
- Baseline establishment  
- Literature-informed replication  
- Structured improvement  
- Model interpretability validation  

---

## Dataset  

**Name:** Knee Osteoarthritis Dataset with Severity Grading  

**Source:** Kaggle (author: Shashwat Tiwari)  

**Classes:** KL 0, KL 1, KL 2, KL 3, KL 4  

**Dataset Structure:** train / val / test  

---

## Methodology  

- Transfer learning using CNN architectures (ResNet18, DenseNet121)  
- Data augmentation and preprocessing  
- Class imbalance handling using WeightedRandomSampler  
- Two-stage training (freeze → fine-tune)  
- Evaluation using accuracy, precision, recall, and macro F1-score  
- Confusion matrix analysis  
- Model interpretability using Grad-CAM  

---

## Current Progress  

- Dataset downloaded and verified locally (train/val/test splits, KL 0–4 labels).  
- EDA completed: class distribution analysis + visual inspection across KL grades.  
- Baseline transfer learning model implemented (ResNet-18 pretrained on ImageNet, 224×224 resolution).  
- Replication model implemented (DenseNet121, 224×224 resolution).  
- Improvement experiment conducted using DenseNet121 with higher input resolution (320×320).  
- Grad-CAM interpretability analysis completed on best-performing model.  

---

## Results Summary  

### Baseline Results (ResNet-18, 224×224)  
- Test Accuracy: ~0.59–0.60  
- Test Macro F1: ~0.62  

### Replication Results (DenseNet121, 224×224)  
- Test Accuracy: ~0.56  
- Test Macro F1: ~0.58  

### Improved Results (DenseNet121, 320×320) – Best Model  
- Test Accuracy: ~0.65  
- Test Macro F1: ~0.65–0.66  

---

## Notes  

- Strong class imbalance observed (KL 4 minority class).  
- Most confusion occurs between adjacent KL grades (e.g., KL1–KL2, KL2–KL3), consistent with subtle radiographic differences.  
- Increasing image resolution significantly improved fine-grained KL discrimination.  
- Grad-CAM visualizations confirm the model focuses on clinically relevant tibiofemoral joint regions rather than background artifacts.  

---

## Reproducibility  

- Dataset is not stored in this repository due to size/licensing constraints.  

**Expected local path:**
- data/raw/knee-osteoarthritis-dataset-with-severity/{train,val,test}


- Training performed on Tesla T4 GPU (Google Colab).  
- Model checkpoints stored externally due to size limits.  

---

## Supervisor  
Prof. Dr. Binh Vu  

## Author  
Reeve  
