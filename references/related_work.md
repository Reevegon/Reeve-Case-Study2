Related Work: Automated Knee Osteoarthritis Analysis from X-ray Images

This section summarizes prior research on automated knee osteoarthritis (KOA) detection and grading using radiographic images. The focus is on deep learning–based approaches, severity grading using the Kellgren–Lawrence (KL) scale, and the use of interpretability techniques to support clinical relevance.

1. Traditional and Early Machine Learning Approaches

Early studies on KOA assessment primarily relied on handcrafted features extracted from knee X-rays, such as texture descriptors, shape features, and joint space width measurements. These features were combined with classical machine learning classifiers, including support vector machines (SVMs) and random forests. While these approaches demonstrated moderate success, their performance was limited by feature engineering complexity and poor generalization across datasets.

The reliance on manual feature extraction also restricted their ability to capture subtle radiographic changes between adjacent KL grades, particularly in early-stage osteoarthritis.

2. Deep Learning for Knee Osteoarthritis Detection

The introduction of convolutional neural networks (CNNs) significantly improved performance in KOA detection tasks. Antony et al. demonstrated that CNNs trained directly on knee X-rays outperform traditional methods by automatically learning discriminative visual features associated with osteoarthritis progression. Their work established deep learning as a viable alternative to manual radiographic scoring.

Subsequent studies further confirmed that CNN-based models can learn clinically relevant patterns such as joint space narrowing and osteophyte formation without explicit feature engineering.

3. KL Severity Grading Using Transfer Learning

Several recent studies have focused on multi-class KL grading rather than binary osteoarthritis detection. Tiulpin et al. proposed deep Siamese and ensemble CNN architectures for KL grading, showing that transfer learning from ImageNet-pretrained models improves convergence and performance, particularly when medical datasets are limited in size.

DenseNet, ResNet, and VGG architectures have been widely adopted in this context due to their strong feature extraction capabilities. However, many studies report persistent confusion between adjacent KL grades, highlighting the inherent difficulty of fine-grained severity classification.

4. Handling Class Imbalance in KOA Datasets

Class imbalance is a recurring challenge in KOA datasets, as severe osteoarthritis cases (KL 4) are less frequent than mild or moderate cases. Several works have addressed this issue using class-weighted loss functions, focal loss, oversampling strategies, or data augmentation.

Despite these techniques, performance on minority classes often remains limited, suggesting that imbalance-aware training strategies alone may be insufficient and should be complemented by better architectural design and interpretability analysis.

5. Interpretability and Explainability in Medical Imaging

Interpretability has become an essential component of medical AI systems. Techniques such as Gradient-weighted Class Activation Mapping (Grad-CAM) have been widely used to visualize regions of interest that influence CNN predictions.

In the context of KOA grading, Grad-CAM visualizations have been shown to highlight clinically meaningful regions, including the tibiofemoral joint space and osteophyte regions. These visual explanations improve clinician trust and provide qualitative validation of model predictions.

6. Positioning of the Present Work

Most existing studies focus either on optimized architectures or ensemble-based solutions with extensive hyperparameter tuning. In contrast, the present work emphasizes a clear, reproducible baseline using a standard transfer learning approach (ResNet-based CNN) combined with systematic exploratory data analysis and transparent evaluation.

The baseline model implemented in this project is not intended to outperform state-of-the-art systems. Instead, it establishes a reference point that:

Confirms the feasibility of automated KL grading on public knee X-ray datasets

Quantifies the impact of class imbalance and KL overlap on performance

Provides a foundation for future improvements, including interpretability analysis using Grad-CAM

This positioning aligns the project with applied research goals and prepares the groundwork for more advanced experimentation in subsequent phases.

7. Key References

Antony, J. et al., Automatic assessment of knee osteoarthritis severity using deep CNNs, IEEE Transactions on Medical Imaging.

Tiulpin, A. et al., Deep learning for knee osteoarthritis severity grading from plain radiographs, Scientific Reports.

Kermany, D. et al., Identifying medical diagnoses using deep learning, Nature Medicine.

Selvaraju, R. et al., Grad-CAM: Visual explanations from deep networks via gradient-based localization, ICCV.

(I will add more refrences as the project progresses.)
