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
- Resolution scaling and regularization refinement  
- Model interpretability validation  

---

## Dataset

**Name:** Knee Osteoarthritis Dataset with Severity Grading  
**Source:** Kaggle (author: Shashwat Tiwari)  
**Classes:** KL 0, KL 1, KL 2, KL 3, KL 4  
**Dataset Structure:** `train / val / test`

### Dataset Size

- **Train:** 5,778 images  
- **Validation:** 826 images  
- **Test:** 1,656 images  

---

## Methodology

### Model Architecture
- Transfer learning using CNN architectures (ResNet18, DenseNet121)  
- ImageNet pretrained weights  

### Training Strategy
- Two-stage training (freeze → fine-tune)  
- AdamW optimizer  
- Cosine learning rate scheduling with warm-up  
- Automatic Mixed Precision (AMP)  
- Exponential Moving Average (EMA)  

### Regularization & Optimization
- Data augmentation (resize, flip, rotation)  
- Class imbalance handling using `WeightedRandomSampler`  
- MixUp augmentation (constant and scheduled)  
- Label smoothing (final model)  

### Evaluation
- Accuracy  
- Precision  
- Recall  
- Macro F1-score  
- Confusion matrix  
- Grad-CAM interpretability analysis  

---

## Current Progress

- Dataset downloaded and verified locally (train/val/test splits, KL 0–4 labels).  
- EDA completed: class distribution analysis + visual inspection across KL grades.  
- Baseline transfer learning model implemented (ResNet-18, 224×224).  
- Replication model implemented (DenseNet121, 224×224).  
- Improvement experiment conducted using DenseNet121 (320×320).  
- Final optimization conducted using DenseNet121 (384×384) with label smoothing and scheduled MixUp.  
- Grad-CAM interpretability analysis completed on best-performing model.  

---

## Results Summary

### Baseline Results (ResNet-18, 224×224)
- **Test Accuracy:** ~0.59–0.60  
- **Test Macro F1:** ~0.62  

### Replication Results (DenseNet121, 224×224)
- **Test Accuracy:** ~0.56  
- **Test Macro F1:** ~0.58  

### Improvement Stage 1 (DenseNet121, 320×320)
- **Test Accuracy:** ~0.67  
- **Test Macro F1:** ~0.69  

### Final Best Model (DenseNet121, 384×384)
- **Test Accuracy:** **0.7089**  
- **Test Macro F1:** **0.7085**  

---

## Notes

- Strong class imbalance observed (KL 4 minority class).  
- Most confusion occurs between adjacent KL grades (KL0–KL1, KL1–KL2).  
- Increasing image resolution (224 → 320 → 384) significantly improved fine-grained KL discrimination.  
- Label smoothing and scheduled MixUp improved stability and reduced overconfidence in borderline cases.  
- Grad-CAM confirms the model focuses on clinically relevant tibiofemoral joint regions.  

---

## Reproducibility

Dataset is not stored in this repository due to size/licensing constraints.

### Expected Local Path
data/raw/knee-osteoarthritis-dataset-with-severity/
├── train/
├── val/
└── test/


- Training performed on Tesla T4 GPU (Google Colab).  
- Model checkpoints stored externally due to size limits.  

---

## Supervisor
Prof. Dr. Binh Vu  

## Author
Reeve  
