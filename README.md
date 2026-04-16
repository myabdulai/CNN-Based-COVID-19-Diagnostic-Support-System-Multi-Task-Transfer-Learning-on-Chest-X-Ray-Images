# CNN-Based-COVID-19-Diagnostic-Support-System-Multi-Task-Transfer-Learning-on-Chest-X-Ray-Images
Deep learning system for chest X-ray analysis using multi-task learning. Combines multiclass classification (COVID-19, Lung Opacity, Viral Pneumonia, Normal) and lung segmentation with a DenseNet121 backbone and Grad-CAM, achieving 0.92 accuracy and 0.986 AUC.

🧠 CNN-Based COVID-19 Diagnostic Support System
Multi-Task Transfer Learning on Chest X-Ray Images
# 📖 Project Overview

This project presents a deep learning–based diagnostic support system for chest X-ray analysis using multi-task learning. The system performs:

✅ Multiclass classification of chest X-rays
✅ Lung segmentation (pixel-level)
✅ Explainability using Grad-CAM

The model classifies images into four clinically relevant categories:
- COVID-19
- Lung Opacity
- Viral Pneumonia
- Normal

# 🎯 Objectives
- Develop a robust multiclass classification model
- Evaluate multi-task learning vs. single-task CNNs
- Improve interpretability using Grad-CAM
- Integrate lung segmentation for anatomical guidance

# 🗂️ Dataset
Source: Kaggle COVID-19 Radiography Database
- Total Images: ~21,000+
Includes:
- Chest X-ray images
- Corresponding lung segmentation masks

# Link to the dataset
https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database

# 📊 Class Distribution
- Class	Count
- Normal	10,192
- Lung Opacity	6,012
- COVID-19	3,616
- Viral Pneumonia	1,345

# 🔀 Data Split
- Training: 70%
- Validation: 15%
- Test: 15%
Images were resized to 224 × 224 and normalized.

# ⚙️ Methodology
- Baseline Models
- EfficientNet
- ResNet
- DenseNet

# Best Model Selection
DenseNet significantly outperformed others and was selected as the backbone.

Fine-Tuning
- Last 40 layers unfrozen
- Learning rate: 1e-5

4️ Multi-Task Learning
- Shared DenseNet encoder
- Classification head
- Segmentation decoder

5️ Weight Transfer Strategy
Instead of using ImageNet weights directly:

The multi-task model was initialized using fine-tuned DenseNet weights, improving convergence and performance.

# 🏗️ Model Architecture
- Encoder: DenseNet121 (pretrained)
- Classification Head:
- Global Average Pooling
- Dense (512)
- Dropout (0.3)
- Softmax output
- Segmentation Head:
- Convolutional decoder (U-Net style)
- Sigmoid output

# 📈 Results
🧪 Final Model (Multi-Task Phase 1.5)
Metric	Value
- Accuracy	0.92
- AUC	0.986
- F1 Score	0.91
- Dice Score	0.89
- IoU	0.80

# 📊 Baseline Comparison
- Model	Accuracy
- EfficientNet	0.48
- ResNet	0.48
- DenseNet	0.82
- Fine-Tuned DenseNet	0.89

# Contributors
Mohammed Yushawu Abdulai: myabdula@mtu.edu/amyshhgh@gmail.com
Peter Mvuma : mvumapeter@gmail.com/pmvuma@mtu.edu

