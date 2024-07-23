# Histopathology Image Analysis for Gastric Cancer Detection: A Hybrid Deep Learning and CatBoost Approach

## 📜 A B S T R A C T
This project focuses on the development of a computer-aided diagnosis (CAD) system for the prompt and accurate detection of gastric cancer, leveraging advanced deep learning techniques. Given the increasing prevalence of gastric cancer, timely diagnosis is critical for effective treatment. Our approach utilizes a hybrid model that combines deep learning with gradient boosting to classify histopathology images effectively. We employed pre-trained models to extract features from the GasHisSDB dataset, which contains gastric histopathological images in varying cropping sizes (80px, 120px, and 160px). The final model integrates the EfficientNetV2B0 for feature extraction and the CatBoost classifier for image classification.
The results demonstrate high accuracy rates of 89.7%, 93.1%, and 93.9% for the respective cropping sizes, with precision, recall, and F1-scores exceeding 0.9. Additionally, we utilized the Grad-CAM algorithm for visualization, confirming that the model focuses on relevant histological features. The t-SNE visualization further illustrated clear clustering between normal and abnormal cases. Our findings highlight the robustness and effectiveness of the proposed method in aiding gastric cancer screening, showcasing its potential for enhancing diagnostic accuracy in clinical settings.

## 📚 Index
- [Abstract](#-a-b-s-t-r-a-c-t)
- [Dataset](#-dataset)
- [Results](#-results)
- [Architecture](#-Architecture)

##  📁 Dataset
The GasHisSDB dataset used in this project contains a comprehensive collection of gastric histopathological images. Below is the distribution of images categorized by cropping size and label (abnormal or normal):

### Table 1: Distribution of Images in the GasHisSDB Dataset

| Cropping Size | Abnormal | Normal  |
|---------------|----------|---------|
| 160px        | 13,124   | 20,160  |
| 120px        | 24,801   | 40,460  |
| 80px         | 59,151   | 87,500  |
| **Total**    | **97,076** | **148,120** |

### Description

- **Cropping Size**: The dimensions of the images used in the dataset.
- **Abnormal**: The number of images classified as abnormal (indicating the presence of gastric cancer).
- **Normal**: The number of images classified as normal (indicating the absence of gastric cancer).

This dataset provides a robust foundation for training and evaluating the proposed deep learning and gradient-boosting model, facilitating accurate classification of gastric histopathology images.

### Reference
For more details about the dataset, you can refer to the following article:
The dataset can be downloaded from the following article:
[GasHisSDB: A new gastric histopathology image dataset for computer-aided diagnosis of gastric cancer](https://www.sciencedirect.com/science/article/abs/pii/S0010482521010015)
By including this reference, you provide users with a direct link to the source of the dataset, enhancing the credibility and usability of your project.

Additionally, GasHisSDB is available at the following URL:  
[GasHisSDB Repository](https://gitee.com/neuhwm/GasHisSDB.git)


## 🏆 Results

### Table 2: Binary Classification Accuracy Score in the GasHisSDB Dataset

| Feature Extractor      | Classifier | 80px | 120px | 160px |
|------------------------|------------|------|-------|-------|
| ResNet50               | CatBoost   | 89.4 | 90.4  | 91.8  |
|                        | LightGBM   | 88.8 | 90.1  | 91.4  |
| VGG16                  | CatBoost   | 87.9 | 89.8  | 90.2  |
|                        | LightGBM   | 87.4 | 89.1  | 89.4  |
| EfficientNetV2B0      | CatBoost   | 89.7 | 93.1  | 93.9  |
|                        | LightGBM   | 89.0 | 92.2  | 92.8  |
| InceptionV3           | CatBoost   | 72.0 | 73.5  | 71.8  |
|                        | LightGBM   | 71.9 | 73.6  | 72.6  |
| ResNet101              | CatBoost   | 88.9 | 91.5  | 92.2  |
|                        | LightGBM   | 88.0 | 90.5  | 91.4  |
| DenseNet201            | CatBoost   | 88.0 | 89.9  | 90.6  |
|                        | LightGBM   | 88.0 | 89.6  | 90.4  |

The results of our experiments demonstrate the effectiveness of various feature extractors and classifiers in achieving high accuracy in gastric cancer detection. Notably, the EfficientNetV2B0 combined with the CatBoost classifier achieved the highest accuracy scores of 89.7%, 93.1%, and 93.9% for the 80px, 120px, and 160px cropping sizes, respectively. Other models, such as ResNet50 and DenseNet201, also showed competitive results, particularly with the CatBoost classifier. In contrast, the InceptionV3 model underperformed compared to the others, highlighting the importance of selecting appropriate architectures for this task. Overall, these results underscore the potential of hybrid approaches in enhancing diagnostic accuracy in medical imaging.


##  🏛️ Architecture
In this section, we provide a brief model architecture diagram.

![Gastric_Cancer_Paper_Revised-5](https://github.com/user-attachments/assets/a0447bb9-16e4-43ba-9eea-d3b9d8e87fe1)

The proposed model architecture explains how it combines EfficientNetV2B0 for feature extraction and CatBoost for classification.
