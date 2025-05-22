# NeuroSpeechBERT

**Fusion of Speech Analysis and BERT-based Deep Learning for Parkinson’s Stage Progression Detection**

NeuroSpeechBERT is a multi-branch deep learning framework developed to detect Parkinson’s Disease (PD) from speech data. By combining acoustic features, spectrograms, and transformer-based NLP models on transcribed speech, this project demonstrates how voice can be used as a reliable, non-invasive biomarker for early PD diagnosis.

---

## Motivation

Parkinson’s Disease affects over 8.5 million people globally, with early symptoms often manifesting in subtle speech changes. Unfortunately, traditional diagnosis relies on subjective clinical evaluation, often delaying intervention by years.

**NeuroSpeechBERT** aims to address this gap through a scalable, AI-powered framework that can process speech to detect PD—making screening more objective, accessible, and feasible even in resource-constrained environments.

---

## Problem Statement

- Traditional diagnostics often overlook early-stage speech anomalies.
- Most research focuses on isolated techniques—either feature-based or deep learning, not both.
- Transcription-based analysis of speech (linguistic/semantic markers) is underexplored in PD.
- There's limited support for real-world, multilingual, or progressive-stage diagnosis.

---

## Project Objectives

1. Leverage **speech signals** as a non-invasive diagnostic medium for early PD detection.
2. Explore **three parallel approaches**: acoustic feature analysis, spectrogram-based CNNs, and transformer-based NLP using transcribed speech.
3. Build a modular, extensible architecture for clinical and research adaptation.

---

## System Architecture

The system comprises **three core modules**:

- **Numerical Feature-Based Models**  
  Extracts handcrafted acoustic/prosodic features (Jitter, Shimmer, MFCC, etc.) and classifies using ML/DL models.

- **Spectrogram-Based CNN Models**  
  Converts audio to Mel spectrograms and applies image classification via EfficientNet, ResNet, and Inception.

- **Speech-to-Text + Transformer Models**  
  Uses OpenAI Whisper ASR for transcription and fine-tunes models like BERT, ELECTRA, RoBERTa, and Albert.

---

## Dataset Details

| Approach              | Dataset Used                                                                 |
|-----------------------|------------------------------------------------------------------------------|
| Numerical Features    | Figshare Parkinson’s Voice Dataset (prolonged vowel sounds)                 |
| Spectrogram Models    | Derived from the same Figshare dataset                                      |
| Text-based Models     | Mozilla Common Voice (Healthy) + SJTU Parkinson Speech Dataset (PD samples) |

> ⚠️ Full datasets are not included in this repository due to size and licensing.  
> Sample `.wav`, metadata, and transcription files are available in the `data/` folder. See `data/README.md` for details.

---

## Tools & Technologies

- **Languages/Frameworks**: Python 3.9, PyTorch, TensorFlow
- **Audio & Speech Processing**: Librosa, OpenSMILE, Parselmouth, Pydub
- **NLP**: Hugging Face Transformers, OpenAI Whisper
- **ML/DL Models**: Random Forest, FNN, CNNs, ELECTRA, BERT, RoBERTa, Albert
- **Utilities**: Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn

---

## Methodology

- **Audio Preprocessing**: Normalization, silence trimming, resampling
- **Feature Extraction**: 67 acoustic/prosodic features → 24 selected
- **Spectrogram Generation**: Mel and log-Mel spectrograms (.png)
- **Transcription**: Whisper ASR for `.wav` to text
- **Text Cleaning**: Lowercasing, punctuation removal, whitespace normalization
- **Training**:
  - **Numerical**: Random Forest, FNN, SVM, Autoencoder
  - **Spectrogram**: EfficientNet-B0, ResNet-50, InceptionV3
  - **Text**: Fine-tuned ELECTRA, BERT, RoBERTa, Albert
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1, AUC-ROC
- **Class Balancing**: SMOTE
- **Tuning**: RandomizedSearchCV (for Random Forest), learning rate schedulers

---

## Results Summary

| Approach              | Best Model       | Test Accuracy | F1 Score | AUC-ROC |
|-----------------------|------------------|---------------|----------|---------|
| Numerical Features    | Random Forest     | 82.35%        | 0.81     | 0.74    |
| Spectrogram Images    | EfficientNet-B0   | 88.24%        | 0.88     | 0.93    |
| Transcribed Text      | ELECTRA           | 98.85%        | 0.99     | 0.997   |

> The text-based approach using ELECTRA delivered the highest performance across all evaluation metrics.

---
## Future Directions
Stage-wise Classification: Move beyond binary prediction to detect early/intermediate stages

Multilingual Support: Train and test on multilingual datasets

Model Ensembling: Combine outputs from all three approaches

Clinical Integration: Build real-time diagnostic tools and deployable systems

## Author
Shikha Chhabra
B.Tech Information Technology
Manipal University Jaipur, 2024–2025

Guided by Prof. Venkatesh Gauri Shankar
Department of Information Technology
