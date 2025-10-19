# ClassMood
ClassMood: An Intelligent Platform for Facial Expression Recognition in Education

1. Project Overview
Description: ClassMood is a facial expression recognition system designed for educational applications. It integrates deep learning models with attention mechanisms to analyze students’ facial expressions in classroom environments. The project implements and compares five models — ResNet18-CBAM, GCN, CapsNet, ViT, and SVM — and demonstrates their performance on both benchmark and real-world classroom scenarios datasets.

2. Dataset Information
Datasets Used: CASME2, MMEW, real-world classroom scenarios datasets.

Categories: 1. Seven facial expression categories (CASME2 and MMEW datasets): disgust, fear, happiness, others, repression, sadness, surprise. 2. Three facial expression categories (real-world classroom scenarios datasets): positive, negative, other.

Split Ratio: 1. Benchmark datasets: 70% training, 15% testing, 15% validation. 2. Real-world classroom scenarios datasets: 100% independent evaluation.

Directory Structure Example:
./train_dataset/
    ├── disgust/
    ├── fear/
    ├── happiness/
    ├── others/
    ├── repression/
    ├── sadness/
    └── surprise/

Preprocessing: Images are resized to 256×256, converted to 3-channel grayscale, and augmented using random rotation, flipping, cropping, and color jittering.

3. Code Information
All model implementations follow the same workflow: data preprocessing, model construction, training, validation/testing, and result output. Only the model definition differs in each file.
Model Construction：
File	Description
CapsNet.py	Capsule Network model
GCN.py	Graph Convolutional Network model
ResNet18_CBAM.py	ResNet18 with CBAM attention mechanism.
SVM.py	Traditional SVM classifier
ViT.py	Vision Transformer model


Web Interface:
File	Description
index.html	Homepage, overview of ClassMood, project goals, and significance
server.html	Upload page for facial expression recognition; connects to backend for prediction
feedback.html	User feedback page with contact information
help.html	Step-by-step usage instructions with screenshots
pre_result.html	Result display page that presents the predicted emotion category after the model completes inference.
flask_app.py	Flask backend integrating the model. 


Usage Instructions (Model Construction)
1.Install dependencies:
pip install -r requirements.txt

2.Prepare dataset in train_dataset/, test_dataset/, val_dataset/ folders

3.Run model:
python ResNet18_CBAM.py (or CapsNet.py, GCN.py, ViT.py, SVM.py)

4.Model weights will be automatically saved as best_model_<modelname>.pth

5.Evaluation metrics (accuracy, macro-F1, confusion matrix) are displayed after training

Usage Instructions (Web interface)
1.Place all HTML files in a web directory and ensure Flask backend is running
2. Access index.html for homepage, server.html to upload images and predict
3. feedback.html and help.html provide user support and guidance

4. Methodology
1. Data Preprocessing: resize, grayscale conversion, augmentation, normalization

2. Model Construction: each Python file defines a specific architecture (ResNet18-CBAM, CapsNet, GCN, ViT, SVM)

3. Training: weighted CrossEntropyLoss for class imbalance, adaptive learning rate scheduler, early stopping

4. Evaluation: Accuracy, Macro-F1, confusion matrices

5. Deployment: integrated into Flask for real-time online recognition

5. Citation
If you use this code, please cite:
Qianyue Zhang. ClassMood: An Intelligent Platform for Facial Expression Recognition in Education. (2025, under review)

6. License
For academic and research use only.
© 2025 Qianyue Zhang. All rights reserved
