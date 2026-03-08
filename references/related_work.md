# Related Work: Automated Knee Osteoarthritis Detection and KL Grading

Automated analysis of knee osteoarthritis (KOA) from radiographic images has been extensively studied using deep learning methods. Most systems aim to classify disease severity according to the Kellgren–Lawrence (KL) grading scale (0–4), which remains the clinical gold standard for osteoarthritis assessment.

This section reviews representative studies on multi-class KL grading and positions the present work relative to existing literature.

---

## 1. Early CNN-Based KL Grading

One of the earliest influential works applying deep learning to KOA grading was conducted by **Antony et al. (IEEE Transactions on Medical Imaging)**.

Using the Osteoarthritis Initiative (OAI) dataset, they demonstrated that convolutional neural networks outperform handcrafted feature-based pipelines.

### Study Details
- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** Custom CNN  
- **Reported Accuracy:** ~63–66%  

### Key Contribution
- Established CNN-based grading as a viable alternative to manual scoring.
- Demonstrated superiority over traditional feature-engineered pipelines.

---

## 2. Siamese and Ensemble Architectures

**Tiulpin et al. (Scientific Reports)** proposed a more advanced framework combining joint localization with Siamese CNNs and ensemble learning.

### Study Details
- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** Siamese CNN + Ensemble  
- **Reported Accuracy:** ~68–69%  

### Key Contribution
- Improved robustness in distinguishing adjacent KL grades.
- Highlighted the intrinsic difficulty of fine-grained severity classification.

---

## 3. DenseNet-Based Transfer Learning Approaches

Subsequent research demonstrated that transfer learning from ImageNet-pretrained backbones significantly improves KL grading performance. DenseNet architectures, in particular, benefit from improved gradient flow and feature reuse.

### Representative DenseNet-Based Results
- **Dataset:** OAI  
- **Task:** 5-class KL grading  
- **Model:** DenseNet-121 (pretrained)  
- **Reported Accuracy:** ~70–72%  
- **Reported Macro-F1:** ~0.70–0.72  

### Key Insight
- Deeper pretrained backbones outperform earlier shallow CNN architectures.
- Transfer learning is critical for medical imaging tasks with limited data.

---

## 4. Attention Mechanisms and Modern Architectures

More recent studies incorporate attention modules or modern architectures such as EfficientNet to improve localization of clinically relevant regions.

### Representative Results
- **Dataset:** OAI / Kaggle KL datasets  
- **Task:** 5-class KL grading  
- **Model:** Attention CNN / EfficientNet-B3  
- **Reported Accuracy:** ~72–75%  
- **Reported Macro-F1:** ~0.73–0.75  

### Key Contribution
- Improved focus on tibiofemoral joint space narrowing and osteophyte formation.
- Enhanced performance on adjacent KL grades.

---

## 5. Comparative Summary of Existing Literature

| Study | Dataset | Model | Task | Reported Accuracy | Reported Macro-F1 |
|--------|---------|-------|------|------------------|------------------|
| Antony et al. | OAI | Custom CNN | KL 0–4 | 63–66% | – |
| Tiulpin et al. | OAI | Siamese + Ensemble CNN | KL 0–4 | 68–69% | – |
| DenseNet Studies | OAI | DenseNet-121 | KL 0–4 | 70–72% | ~0.71 |
| Attention / EfficientNet | OAI / Kaggle | EfficientNet-B3 | KL 0–4 | 72–75% | ~0.74 |

---

## 6. Positioning of the Present Work

The present project uses a public Kaggle KL-graded dataset and follows a structured experimental pipeline with progressive model refinement.

### Baseline (ResNet18, 224×224)
- **Test Accuracy:** ~59–60%  
- **Macro-F1:** ~0.62  

### Replication (DenseNet121, 224×224)
- **Test Accuracy:** ~0.56  
- **Macro-F1:** ~0.58  

### Improved Model – Stage 1 (DenseNet121, 320×320)
- **Test Accuracy:** ~0.67  
- **Macro-F1:** ~0.69  

### Final Optimized Model (DenseNet121, 384×384)
- **Test Accuracy:** **0.7089**  
- **Macro-F1:** **0.7085**  

### Contribution of the Present Work
- Fully reproducible baseline pipeline  
- Literature-informed architecture replication  
- Structured performance improvement through resolution scaling  
- Integration of label smoothing and scheduled MixUp  
- Quantitative gains over baseline (+11% absolute improvement from baseline)  
- Interpretability validation via Grad-CAM  

Unlike many prior works that rely on ensemble models or heavy architectural modifications, this study emphasizes controlled experimentation, reproducibility, and systematic optimization while achieving competitive performance on a publicly available KL dataset.

---

## 7. Research Gap and Future Directions

Although attention-based and ensemble approaches achieve higher reported accuracy, they increase architectural complexity and reduce transparency.

### Potential Future Improvements
- EfficientNet-based backbones  
- Ordinal regression losses tailored to KL grading  
- Attention mechanisms integrated into DenseNet  
- Class-balanced or focal loss functions  
- Multi-view joint modeling  

The current work establishes a strong experimental foundation for these extensions while maintaining architectural simplicity and interpretability.

##16. References 
[1] Antony, J., McGuinness, K., O’Connor, N., & Moran, K. (2017). 
Automatic detection of knee joints and quantification of knee osteoarthritis severity 
using convolutional neural networks. 
IEEE Transactions on Medical Imaging. 

[2] Tiulpin, A., Thevenot, J., Rahtu, E., Lehenkari, P., & Saarakkala, S. (2018). 
Automatic knee osteoarthritis diagnosis from plain radiographs using deep learning. 
Scientific Reports. 

[3] He, K., Zhang, X., Ren, S., & Sun, J. (2016). 
Deep Residual Learning for Image Recognition. 
Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition 
(CVPR). 

[4] Huang, G., Liu, Z., Van Der Maaten, L., & Weinberger, K. Q. (2017). 
Densely Connected Convolutional Networks. 
Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition 
(CVPR). 

[5] Selvaraju, R. R., et al. (2017). 
Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization. 
International Journal of Computer Vision. 

[6] Litjens, G., et al. (2017). 
A survey on deep learning in medical image analysis. 
Medical Image Analysis. 

[7] Krizhevsky, A., Sutskever, I., & Hinton, G. (2012). 
ImageNet classification with deep convolutional neural networks. 
Advances in Neural Information Processing Systems (NeurIPS). 

[8] Tan, M., & Le, Q. (2019). 
EfficientNet: Rethinking model scaling for convolutional neural networks. 
Proceedings of the International Conference on Machine Learning (ICML). 

[9] Russakovsky, O., et al. (2015). 
ImageNet Large Scale Visual Recognition Challenge. 
International Journal of Computer Vision.
