# Related Work: Automated Knee Osteoarthritis Detection and KL Grading

Automated analysis of knee osteoarthritis (KOA) from radiographic images has been widely studied using machine learning and, more recently, deep learning approaches. Most modern systems aim to classify severity according to the Kellgren–Lawrence (KL) grading scale (0–4), which remains the clinical standard for OA assessment.

This section summarizes representative studies on multi-class KL grading and positions the present work relative to existing methods.

---

## 1. Early Deep Learning Approaches

One of the first works demonstrating the effectiveness of convolutional neural networks (CNNs) for KL grading was conducted by **Antony et al. (IEEE Transactions on Medical Imaging)**. Using the Osteoarthritis Initiative (OAI) dataset, they showed that CNN-based models outperform traditional handcrafted feature pipelines.

- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** Custom CNN  
- **Reported Accuracy:** ~63–66%

This study established CNN-based grading as a viable alternative to manual scoring and traditional machine learning methods.

---

## 2. Ensemble and Siamese Architectures

**Tiulpin et al. (Scientific Reports)** introduced a more advanced approach combining joint localization with Siamese CNN and ensemble learning techniques.

- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** Siamese CNN + Ensemble  
- **Reported Accuracy:** ~68–69%

Their work demonstrated that incorporating joint alignment and ensemble strategies improves robustness, particularly in distinguishing adjacent KL grades.

---

## 3. Transfer Learning with DenseNet Architectures

Subsequent research has shown that transfer learning significantly enhances KL grading performance. DenseNet-based models, in particular, have demonstrated strong performance due to improved gradient flow and feature reuse.

Representative DenseNet-based studies report:

- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** DenseNet-121 (ImageNet pretrained)  
- **Reported Accuracy:** ~70–72%  
- **Reported Macro-F1:** ~0.71  

These results indicate that deeper pretrained backbones outperform earlier shallow CNN architectures.

---

## 4. Attention-Based and Modern Architectures

More recent studies incorporate attention mechanisms or modern architectures such as EfficientNet.

- **Dataset:** OAI or Kaggle KL dataset  
- **Task:** 5-class KL grading  
- **Model:** Attention CNN / EfficientNet-B3  
- **Reported Accuracy:** ~72–75%  
- **Reported Macro-F1:** ~0.74  

Attention mechanisms help the network focus on clinically relevant regions such as tibiofemoral joint space narrowing and osteophyte formation.

---

## 5. Comparative Summary of Existing Work

| Study                              | Dataset         | Model                         | Task      | Reported Accuracy | Reported Macro-F1 |
|-------------------------------------|----------------|------------------------------|-----------|------------------|------------------|
| Antony et al.                      | OAI            | Custom CNN                  | KL 0–4    | 63–66%           | –                |
| Tiulpin et al.                     | OAI            | Siamese + Ensemble CNN      | KL 0–4    | 68–69%           | –                |
| DenseNet-based studies             | OAI            | DenseNet-121                | KL 0–4    | 70–72%           | ~0.71            |
| Attention / EfficientNet studies   | OAI / Kaggle   | EfficientNet-B3             | KL 0–4    | 72–75%           | ~0.74            |

---

## 6. Positioning of the Present Work

The present project establishes a reproducible baseline using a transfer learning–based ResNet18 architecture on a public knee X-ray dataset with KL grading. The baseline achieves:

- **Test Accuracy:** ~59–60%  
- **Macro-F1:** ~0.62  

While slightly below reported DenseNet and attention-based methods in the literature, this baseline provides:

1. A transparent and reproducible training pipeline  
2. Systematic imbalance handling analysis  
3. A foundation for replication and controlled improvement  

In the next phase, a DenseNet-121–based architecture will be implemented to replicate reported literature performance and evaluate whether similar gains can be achieved under the current dataset configuration.
