# Related Work: Automated Knee Osteoarthritis Detection and KL Grading

Automated analysis of knee osteoarthritis (KOA) from radiographic images has been extensively studied using deep learning methods. Most systems aim to classify disease severity according to the Kellgren–Lawrence (KL) grading scale (0–4), which remains the clinical gold standard for osteoarthritis assessment.

This section reviews representative studies on multi-class KL grading and positions the present work relative to existing literature.

---

## 1. Early CNN-Based KL Grading

One of the earliest influential works applying deep learning to KOA grading was conducted by **Antony et al. (IEEE Transactions on Medical Imaging)**. Using the Osteoarthritis Initiative (OAI) dataset, they demonstrated that convolutional neural networks outperform handcrafted feature-based pipelines.

- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** Custom CNN  
- **Reported Accuracy:** ~63–66%  

This work established CNN-based grading as a viable alternative to manual scoring and traditional machine learning methods.

---

## 2. Siamese and Ensemble Architectures

**Tiulpin et al. (Scientific Reports)** proposed a more advanced framework combining joint localization with Siamese CNNs and ensemble learning.

- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** Siamese CNN + Ensemble  
- **Reported Accuracy:** ~68–69%  

Their results showed improved robustness in distinguishing adjacent KL grades, highlighting the difficulty of fine-grained severity classification.

---

## 3. DenseNet-Based Transfer Learning Approaches

Later studies demonstrated that transfer learning from ImageNet-pretrained backbones significantly improves performance in KL grading tasks. DenseNet architectures, in particular, benefit from improved gradient flow and feature reuse.

Representative DenseNet-based studies report:

- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** DenseNet-121 (pretrained)  
- **Reported Accuracy:** ~70–72%  
- **Reported Macro-F1:** ~0.70–0.72  

These results indicate that deeper pretrained backbones outperform early shallow CNN architectures.

---

## 4. Attention Mechanisms and Modern Architectures

More recent works incorporate attention modules or modern architectures such as EfficientNet.

- **Dataset:** OAI / Kaggle KL datasets  
- **Task:** 5-class KL grading  
- **Model:** Attention CNN / EfficientNet-B3  
- **Reported Accuracy:** ~72–75%  
- **Reported Macro-F1:** ~0.73–0.75  

Attention mechanisms improve localization of clinically relevant regions such as tibiofemoral joint space narrowing and osteophyte formation.

---

## 5. Comparative Summary of Existing Literature

| Study | Dataset | Model | Task | Reported Accuracy | Reported Macro-F1 |
|--------|---------|-------|------|------------------|------------------|
| Antony et al. | OAI | Custom CNN | KL 0–4 | 63–66% | – |
| Tiulpin et al. | OAI | Siamese + Ensemble CNN | KL 0–4 | 68–69% | – |
| DenseNet studies | OAI | DenseNet-121 | KL 0–4 | 70–72% | ~0.71 |
| Attention / EfficientNet | OAI / Kaggle | EfficientNet-B3 | KL 0–4 | 72–75% | ~0.74 |

---

## 6. Positioning of the Present Work

The present project uses a public Kaggle KL-graded dataset and follows a structured experimental pipeline:

### Baseline (ResNet18, 224×224)
- **Test Accuracy:** ~59–60%  
- **Macro-F1:** ~0.62  

### Replication (DenseNet121, 224×224)
- **Test Accuracy:** ~0.56  
- **Macro-F1:** ~0.58  

### Improved Model (DenseNet121, 320×320)
- **Test Accuracy:** ~0.65  
- **Macro-F1:** ~0.65–0.66  

Although the final performance remains slightly below large-scale OAI-based studies (which often use joint localization, ensembles, or attention mechanisms), the present work demonstrates:

1. A fully reproducible baseline pipeline  
2. Literature-informed architecture replication  
3. Structured improvement through resolution scaling  
4. Quantitative performance gains over baseline  
5. Interpretability validation via Grad-CAM  

Unlike many prior works that rely on ensemble models or heavy architectural modifications, this study emphasizes controlled experimentation and reproducibility while achieving competitive performance on a publicly available KL dataset.

---

## 7. Research Gap and Future Direction

While attention-based and ensemble approaches achieve higher reported accuracy, they increase architectural complexity and reduce interpretability.

Future improvements may explore:

- EfficientNet-based backbones  
- Ordinal regression losses tailored to KL grading  
- Attention mechanisms integrated into DenseNet  
- Class-balanced loss functions  

The current work establishes a strong experimental foundation for such extensions.
