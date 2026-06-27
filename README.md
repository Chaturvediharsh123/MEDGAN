# 🧠 MedGAN

### Synthetic Brain MRI Generation using Conditional GANs for Brain Tumor Data Augmentation

> **MedGAN** is a deep learning project that leverages **Conditional Generative Adversarial Networks (cGANs)** to generate realistic synthetic Brain MRI images for different brain tumor classes. The project aims to address one of the biggest challenges in medical AI—**limited and imbalanced datasets**—by producing high-quality synthetic MRI scans that can improve the performance of downstream brain tumor classification models.

---

# 📖 Overview

Medical imaging datasets are often small, expensive to annotate, and restricted due to patient privacy regulations. These limitations make it difficult to train robust deep learning models, especially for rare diseases and underrepresented tumor classes.

MedGAN learns the underlying distribution of Brain MRI images and generates synthetic scans that closely resemble real patient data. These generated images can be used for:

* Data augmentation
* Research and experimentation
* Improving class balance
* Training medical AI models
* Educational purposes

The effectiveness of the generated images is validated by comparing the performance of a brain tumor classifier trained on:

* Real MRI images only
* Real MRI images + Synthetic MRI images

---

# 🎯 Problem Statement

Brain tumor diagnosis using MRI scans has become one of the most important applications of Artificial Intelligence in healthcare.

However, building reliable deep learning models faces several challenges:

* Limited availability of annotated MRI datasets
* Severe class imbalance among tumor types
* Privacy concerns preventing data sharing
* High cost of acquiring medical images
* Poor generalization caused by insufficient training data

MedGAN addresses these challenges by generating realistic synthetic MRI images that increase dataset diversity while preserving patient privacy.

---

# 🎯 Objectives

The primary objectives of this project are:

* Generate realistic Brain MRI images using Generative Adversarial Networks.
* Develop a Conditional GAN capable of generating specific tumor classes.
* Improve dataset diversity using synthetic MRI images.
* Evaluate image quality using quantitative metrics.
* Compare classifier performance before and after synthetic data augmentation.
* Build an end-to-end deployable AI application using FastAPI and Streamlit.

---

# 🧠 Brain Tumor Classes

The model is designed to generate MRI images for multiple brain tumor categories.

Supported classes:

* Glioma
* Meningioma
* Pituitary Tumor
* No Tumor (Healthy Brain)

---

# ✨ Features

## Synthetic MRI Generation

Generate realistic Brain MRI images from random latent vectors.

---

## Conditional Image Generation

Generate MRI scans for a selected tumor category.

Example:

```
Input:

Tumor Type = Glioma

↓

Generated MRI Scan
```

---

## Dataset Augmentation

Automatically generate thousands of synthetic MRI scans to increase dataset diversity and reduce class imbalance.

---

## Model Evaluation

Evaluate generated images using:

* Fréchet Inception Distance (FID)
* Inception Score (IS)
* Precision & Recall for Generative Models (optional)
* Visual comparison with real MRI images

---

## Classifier Comparison

Evaluate whether synthetic data improves brain tumor classification by comparing:

* Real dataset only
* Real + Synthetic dataset

Metrics include:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

---

## REST API

Generate MRI scans programmatically using FastAPI.

Example endpoints:

```
POST /generate
POST /generate/{tumor_type}
GET /metrics
```

---

## Interactive Dashboard

A Streamlit dashboard allows users to:

* Select tumor type
* Generate MRI scans
* Download generated images
* View training progress
* Monitor evaluation metrics
* Compare generated and real MRI scans

---

# 🏗 Project Architecture

```
                     Brain MRI Dataset
                              │
                              ▼
                    Data Collection
                              │
                              ▼
                   Data Cleaning & EDA
                              │
                              ▼
                    Image Preprocessing
                              │
                              ▼
                  Train / Validation Split
                              │
                              ▼
                     Conditional GAN
              ┌─────────────────────────────┐
              │                             │
              │     Generator               │
              │            ▲                │
              │            │                │
              │   Random Noise + Label      │
              │            │                │
              │            ▼                │
              │   Synthetic MRI Images      │
              │                             │
              └─────────────┬───────────────┘
                            │
                            ▼
                     Discriminator
                            │
                            ▼
                    Real or Fake Decision
                            │
                            ▼
                     Model Optimization
                            │
                            ▼
               Synthetic MRI Image Dataset
                            │
                            ▼
              Brain Tumor Classification
                            │
                            ▼
          Performance Comparison & Analysis
                            │
                            ▼
               FastAPI + Streamlit Dashboard
```

---

# 🧠 Model Pipeline

```
Medical Images

↓

Preprocessing

↓

Conditional GAN Training

↓

Synthetic MRI Generation

↓

Image Quality Evaluation

↓

Synthetic Dataset Creation

↓

Brain Tumor Classification

↓

Performance Comparison

↓

Deployment
```

---

# 📊 Evaluation Metrics

## Image Generation

* Fréchet Inception Distance (FID)
* Inception Score (IS)
* Precision
* Recall
* Loss Curves

---

## Classification

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC (where applicable)
* Confusion Matrix

---

# 💻 Technology Stack

## Deep Learning

* PyTorch

## Computer Vision

* OpenCV
* Pillow

## Data Processing

* NumPy
* Pandas

## Visualization

* Matplotlib

## API

* FastAPI

## Frontend

* Streamlit

## Metrics

* TorchMetrics
* scikit-image

---

# 📂 Project Structure

```
MedGAN/
│
├── data/
│   ├── raw/
│   ├── processed/
│   ├── train/
│   ├── validation/
│   └── test/
│
├── notebooks/
│
├── models/
│   ├── generator.py
│   ├── discriminator.py
│   ├── cgan.py
│   ├── wgan_gp.py
│   └── losses.py
│
├── training/
│   ├── train.py
│   ├── evaluate.py
│   ├── inference.py
│   └── checkpoints.py
│
├── classifier/
│   ├── train_classifier.py
│   └── evaluate_classifier.py
│
├── metrics/
│   ├── fid.py
│   ├── inception_score.py
│   └── visualization.py
│
├── api/
│   └── main.py
│
├── dashboard/
│   └── app.py
│
├── outputs/
│
├── saved_models/
│
├── requirements.txt
│
├── Dockerfile
│
└── README.md
```

---

# 🚀 Future Improvements

* StyleGAN2 integration
* WGAN-GP for improved training stability
* Multi-modal MRI generation
* Diffusion model comparison
* Explainable AI integration
* Federated learning support
* 3D MRI volume generation
* Synthetic segmentation mask generation
* Multi-class tumor synthesis
* Cloud deployment with GPU inference

---

# ⚠ Disclaimer

This project is intended for **research, education, and data augmentation purposes only**.

The generated MRI images are synthetic and **must not be used for clinical diagnosis, treatment planning, or medical decision-making** without rigorous validation and approval by qualified medical professionals.

---

# 🌟 Expected Outcomes

* High-quality synthetic Brain MRI images
* Reduced class imbalance
* Improved classifier performance through data augmentation
* End-to-end deployable medical AI system
* Reproducible research workflow
* Strong portfolio project demonstrating Generative AI, Computer Vision, Medical Imaging, and Deep Learning expertise

---

# 🤝 Contributions

Contributions, bug reports, feature requests, and research collaborations are welcome. Feel free to fork the repository, submit pull requests, or open issues to improve the project.

---

# 📄 License

This project is released under the **MIT License** and is intended for academic research and educational use.
