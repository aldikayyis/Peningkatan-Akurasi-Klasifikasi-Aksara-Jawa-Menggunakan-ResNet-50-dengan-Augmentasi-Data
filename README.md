# Javanese Script Classification using Deep Learning with Extreme Data Augmentation

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red)
![Streamlit](https://img.shields.io/badge/Streamlit-Web%20App-FF4B4B)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview
**Indonesian:**
Proyek ini adalah implementasi Tugas Akhir berjudul *"Implementasi Augmentasi Data untuk Meningkatkan Akurasi Klasifikasi Citra Aksara Jawa Berbasis Deep Learning"*. Penelitian ini mengembangkan sistem pengenalan 20 kelas aksara Jawa dasar (Hanacaraka) menggunakan arsitektur **ResNet-50** dengan strategi **Transfer Learning**.

Masalah utama yang diangkat adalah keterbatasan dataset yang menyebabkan *overfitting*. Solusi yang ditawarkan adalah penerapan **Extreme Data Augmentation** untuk meningkatkan generalisasi model.

**English:**
This repository contains the implementation of a Bachelor's Thesis on Javanese Script Classification. The project utilizes **ResNet-50** architecture with **Transfer Learning** to classify 20 basic Javanese characters (Hanacaraka). To address dataset scarcity and overfitting, an **Extreme Data Augmentation** technique is applied, significantly improving model robustness and generalization.

## 🚀 Key Features
* **Deep Learning Model:** ResNet-50 pre-trained on ImageNet, fine-tuned for Javanese script.
* **Extreme Augmentation:** Dynamic, on-the-fly transformations including Rotation, Color Jitter, Texture Blending, Gaussian Noise, and Elastic Transform.
* **Web Application:** A user-friendly interface built with **Streamlit** for real-time image classification.
* **High Performance:** Achieved **92.00% Test Accuracy** and **91.63% F1-Score**.

## 📂 Dataset
The dataset used is the **Indonesian Local Script Characters** (focusing on the Javanese script subset).
* **Total Images:** 11,557 images.
* **Classes:** 20 Basic Characters (Ba, Ca, Da, Dha, Ga, Ha, Ja, Ka, La, Ma, Na, Nga, Nya, Pa, Ra, Sa, Ta, Tha, Wa, Ya).
* **Split:** 80% Training, 10% Validation, 10% Testing.

## 🛠️ Methodology
### 1. Preprocessing
* **Resize:** 224x224 pixels.
* **Normalization:** Using ImageNet mean and standard deviation.
* **Conversion:** Grayscale to RGB (3 channels).

### 2. Augmentation Pipeline
To combat overfitting, the **Model B (Proposed Method)** utilizes a robust augmentation pipeline:
* Random Rotation (±15°)
* Color Jitter (Brightness, Contrast, Saturation)
* Gaussian Noise & Blur
* Elastic Transformation
* Affine Transformations (Shear, Scale)

### 3. Model Architecture
* **Backbone:** ResNet-50 (Frozen base layers initially).
* **Head:** Custom Fully Connected Layer (Dropout 0.3 + Linear Layer for 20 classes).
* **Optimizer:** Adam.
* **Loss Function:** Categorical Crossentropy.

## 📊 Results & Evaluation
Comparison between **Model A** (Baseline/No Augmentation) and **Model B** (Extreme Augmentation):

| Metric | Model A (No Augmentation) | Model B (Extreme Augmentation) | Improvement |
| :--- | :---: | :---: | :---: |
| **Validation Accuracy** | 99.88% | 99.19% | - |
| **Test Accuracy** | **75.00%** | **92.00%** | **+17.00%** |
| **Generalization Gap** | 24.88% (Overfit) | **7.19% (Good)** | - |
| **F1-Score (Weighted)** | 75.07% | **91.63%** | **+16.56%** |

> **Conclusion:** Extreme augmentation successfully reduced overfitting and significantly improved the model's ability to generalize to new, unseen data.

## 💻 Installation & Usage

### Prerequisites
* Python 3.8+
* PyTorch
* Streamlit

### 1. Clone the Repository
```bash
git clone [https://github.com/username/javanese-script-classification.git](https://github.com/username/javanese-script-classification.git)
cd javanese-script-classification
```
### 2. Install Depedencies
```bash
pip install -r requirements.txt
```
3. Run the Streamlit App
```bash
streamlit run app.py
```
📸 Demo
(Anda bisa menambahkan screenshot aplikasi Streamlit di sini)

👤 Author
Aldi Smart Nur Irfansyah

Informatics Engineering

Universitas Muhammadiyah Malang

Student ID: 202110370311133

📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgements
Universitas Muhammadiyah Malang

Mendeley Data for the "Indonesian Local Script Characters" dataset.
