# Predictive Framework for Early Multi-Disease Screening in Smart Healthcare Ecosystem

[![GitHub Repo](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/yourusername/your-repo)
[![Paper](https://img.shields.io/badge/Paper-PDF-red?logo=adobeacrobatreader)](link-to-paper)
[![Award](https://img.shields.io/badge/Award-Best%20Paper%20ICRTET2026-gold?logo=medal)]()
[![Conference](https://img.shields.io/badge/Conference-ICRTET%202026-ff69b4)](https://)
[![License](https://img.shields.io/badge/License-MIT-green)]()

**Authors:** Rehan I. Mokashi, Manish D. Sandanshiv, Prof. Komal S. Gandle  
**Affiliation:** Government College of Engineering, Karad, Maharashtra, India  
**Contact:** [rehanmokashi786@gmail.com](mailto:rehanmokashi786@gmail.com).

**Conference:** International Conference on Recent Trends in Engineering and Technology (ICRTET 2026), D. Y. Patil College of Engineering & Technology, Kasaba Bawada, Kolhapur.  
**Status:** ✅ Presented | ✅ Scopus-indexed | ✅ IEEE-supported | ✅ AICTE sponsored  
**Award:** 🏆 **Best Research Paper Award** (Winner)

---

## 📑 Table of Contents
- [Abstract](#-abstract)
- [Award & Recognition](#-award--recognition)
- [Key Features](#-key-features)
- [Methodology](#-methodology)
- [Datasets](#-datasets)
- [Results](#-results)
  - [Comparative Performance](#comparative-performance)
  - [Feature Importance](#feature-importance-heart-disease)
  - [Ablation Study](#ablation-study)
- [Code Implementation](#-code-implementation)
- [Citation](#-citation)
- [Acknowledgments](#-acknowledgments)
- [Contact & Links](#-contact--links)

---

## 📖 Abstract

The implementation of artificial intelligence in healthcare has transformed the way diseases are predicted and screened early. This study suggests a new predictive approach to early screening of multi-diseases in a smart health system that can be characterized by using heterogeneous health information provided by IoT devices, electronic health records (EHRs), and medical imaging. Through a hybrid machine learning and deep learning architecture—with the use of Convolutional Neural Networks (CNNs) to analyze image-based diagnostics and ensemble algorithms (XGBoost, Random Forest) to analyze structured clinical data—the framework allows identifying multiple pathologies (cardiovascular, oncological, and infectious diseases) at once. The system is developed to allow real-time analysis, interoperability, and scalability, ensuring smooth integration into existing healthcare infrastructures. High accuracy, robustness, and clinical relevance have been proven after experimental validation on a variety of datasets, providing a proactive, personalized, and efficient solution to preventive healthcare. The framework aims to minimize delays in the diagnostic process, enhance patient outcomes, and maximise resource allocation in modern medical practice.

---

## 🏆 Award & Recognition

We are thrilled to announce that our research received the **Best Research Paper Award** at **ICRTET 2026**! The conference was held at D. Y. Patil College of Engineering & Technology, Kolhapur, and featured eminent keynote speakers including:

- **Prof. Michael J. Pont** (Teesside University, UK)
- **Prof. Nilanjan Dey**
- **Dr. Kalaivani Chellappan, PhD, PTech** (UKM, Malaysia)
- **Dr. Manisha Bhanuse** (Convenor)

We extend our sincere gratitude to the organizers, session chairs, and mentors for their valuable feedback.

![20140207_080000 jpg](https://github.com/user-attachments/assets/6519d522-c87a-4b5b-b74e-f0bc46f5c624)
*Best Research Paper Award Certificate*

  ![IMG-20260206-WA0153 jpg](https://github.com/user-attachments/assets/5f405937-e2e0-4eb8-b494-360d242f9578)![WhatsApp Image 2026-02-07 at 09 57 18](https://github.com/user-attachments/assets/27cef204-ff7a-4f6e-a408-96ffdc968f49)

*Receiving the award at ICRTET 2026*

For more details, see our [LinkedIn post](https://www.linkedin.com/posts/rehan-i-mokashi-7b32472a2_icrtet-dyp-2026-activity-7425789791105097728-FwyH?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEkBr7cBmGiBklLUnPEkWqhoUHLISoyobQ8).

---

## ✨ Key Features

- **Multi-Disease Screening:** Simultaneous detection of COVID-19, brain tumors, heart disease, thoracic conditions, and skin lesions.
- **Hybrid Architecture:** Combines CNNs (EfficientNetB4) for image analysis with XGBoost/DNN for structured clinical data.
- **Multimodal Data Fusion:** Integrates medical images (X-ray, MRI, dermatoscopy) and tabular data (EHRs, lab tests, symptoms).
- **Real-Time & Scalable:** Microservices-based deployment with 47ms inference time, suitable for smart healthcare ecosystems.
- **Explainability:** Feature importance analysis and CNN attention maps for clinical interpretability.
- **Privacy-Preserving:** Federated learning ready, with de-identification and TLS 1.3 encryption.

---

## 🧠 Methodology

The proposed framework follows a late-fusion strategy:
<img width="531" height="752" alt="Flow" src="https://github.com/user-attachments/assets/7f41f079-1d0f-40d7-b177-962e5a6aad0e" />

  
*System Workflow (Data Preparation → Parallel CNN & Tabular Branches → Fusion → Classification → Decision Support)*

1. **Data Preparation:** Preprocessing of images (resizing, normalization) and tabular data (encoding, scaling, handling missing values).
2. **Image Branch:** EfficientNetB4 with transfer learning extracts deep features from medical images.
3. **Tabular Branch:** XGBoost ensemble and a Deep Neural Network process structured clinical data (lab results, symptoms, demographics).
4. **Fusion Layer:** Concatenated features from both branches are fed into a multilayer perceptron for multi-label classification.
5. **Output:** Probabilities for multiple disease classes, integrated with clinical decision support.

The system is containerized using Docker and orchestrated with Kubernetes, enabling deployment on cloud and edge devices.

---

## 📊 Datasets

The framework was trained and validated on a diverse set of public datasets:

| Disease Category   | Dataset Source     | Data Modality       | Reference |
|--------------------|--------------------|---------------------|-----------|
| COVID-19           | COVIDx             | X-Ray Images        | [1]       |
| Thoracic Diseases  | ChestX-ray14       | X-Ray Images        | [17]      |
| Brain Tumor        | Brain Tumor MRI    | MRI Images          | [10]      |
| Skin Lesions       | HAM10000           | Dermatoscopy        | [11]      |
| Heart Disease      | UCI Heart Disease  | Clinical (Tabular)  | [8]       |
| General Symptoms   | Symptom-Disease    | Text/Categorical    | [4]       |

*Note: Detailed dataset sizes and splits are available in the paper.*

---

## 📈 Results

### Comparative Performance

| Disease Category   | Model Type           | Accuracy (%) | F1-Score | AUC-ROC | Hamming Loss |
|--------------------|----------------------|--------------|----------|---------|--------------|
| **COVID-19**       | **Proposed Hybrid**  | **96.8**     | **0.952**| **0.985**| **0.031**    |
|                    | CNN-only [1]         | 94.2         | 0.921    | 0.962   | 0.058        |
|                    | XGBoost-only         | 87.5         | 0.842    | 0.901   | 0.125        |
| **Brain Tumor**    | **Proposed Hybrid**  | **97.5**     | **0.961**| **0.990**| **0.025**    |
|                    | CNN-only [10]        | 95.8         | 0.938    | 0.972   | 0.042        |
|                    | RF-only              | 89.2         | 0.863    | 0.912   | 0.108        |
| **Heart Disease**  | **Proposed Hybrid**  | **91.7**     | **0.902**| **0.943**| **0.083**    |
|                    | XGBoost-only [8]     | 89.3         | 0.876    | 0.921   | 0.107        |
|                    | CNN-only             | 85.4         | 0.827    | 0.882   | 0.146        |
| **Multi-disease Avg.** | **Proposed Hybrid** | **93.2**  | **0.918**| **0.963**| **0.069**    |
|                    | Best Single model    | 90.1         | 0.885    | 0.932   | 0.099        |

The hybrid framework consistently outperforms single-modality approaches, with significant gains in imaging tasks while maintaining competitive performance on tabular data.

### Feature Importance (Heart Disease)
<img width="835" height="790" alt="download (1)" src="https://github.com/user-attachments/assets/9f1b9e98-a711-4d3c-9f58-2f5a3e43c8ca" />

  
*XGBoost feature importance for heart disease prediction – values align with clinical literature (e.g., serum cholesterol, maximum heart rate, chest pain type).*

| Feature                 | Importance (%) |
|-------------------------|----------------|
| Serum Cholesterol       | 23.1%          |
| Maximum Heart Rate      | 19.8%          |
| Chest Pain Type         | 16.4%          |
| ST Depression           | 13.2%          |
| Age                     | 10.5%          |
| Resting Blood Pressure  | 8.7%           |
| Sex                     | 4.3%           |
| Others                  | 4.0%           |

### Ablation Study

| Configuration                     | Accuracy (%) | Δ vs. Full Model |
|-----------------------------------|--------------|------------------|
| Full Hybrid Framework             | 93.2         | –                |
| Without XGBoost (CNN+CNN only)    | 90.4         | -2.8             |
| Without CNN (XGBoost+CNN only)    | 88.7         | -4.5             |
| Without Feature Fusion            | 89.1         | -4.1             |
| Without Transfer Learning         | 91.5         | -1.7             |

All components contribute substantially, with the CNN branch and feature fusion being most critical.

---

## 💻 Code Implementation

The codebase for this research is currently being prepared for public release. It includes:

- Data preprocessing scripts (image augmentation, tabular encoding, SMOTE for imbalance)
- Model training pipelines (TensorFlow 2.10, Scikit-learn, XGBoost)
- Microservices deployment (Docker, Kubernetes) with REST API (Node.js)
- Evaluation scripts for multi-label metrics

We plan to open-source the code soon. For early access or collaboration inquiries, please contact the authors.

---

## 📝 Citation

If you find this work useful in your research, please cite our paper (once published by IEEE) or use the following BibTeX entry:

```bibtex
@inproceedings{mokashi2026predictive,
  title={Predictive Framework for Early Multi-Disease Screening in Smart Healthcare Ecosystem},
  author={Mokashi, Rehan I. and Sandanshiv, Manish D. and Gandle, Komal S.},
  booktitle={International Conference on Recent Trends in Engineering and Technology (ICRTET)},
  year={2026},
  organization={IEEE}
}
```

---

## 🙏 Acknowledgments

We thank our institution, **Government College of Engineering, Karad**, for continuous support and resources. We are grateful to the conference organizers of **ICRTET 2026** and the session chairs for their insightful comments. Special thanks to the keynote speakers **Prof. Michael J. Pont**, **Prof. Nilanjan Dey**, **Dr. Kalaivani Chellappan**, and **Dr. Manisha Bhanuse** for inspiring talks and encouragement.

---

## 📫 Contact & Links

- **Rehan I. Mokashi:** [rehanmokashi786@gmail.com](rehanmokashi786@gmail.com)   

**Links:**  
- [LinkedIn Post: Best Paper Award Announcement](https://www.linkedin.com/posts/rehan-i-mokashi-7b32472a2_icrtet-dyp-2026-activity-7425789791105097728-FwyH?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEkBr7cBmGiBklLUnPEkWqhoUHLISoyobQ8)  
- [Conference Website: ICRTET 2026](https://dypcet.in/ICRTET-2026/)

---
