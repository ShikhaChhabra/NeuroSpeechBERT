# Data Overview

This project uses different datasets across its three branches due to the nature of the input required by each approach.

---

### 1. Numerical Feature-Based Approach
- **Dataset Source**: Figshare - "Voice Samples for Patients with Parkinson's Disease and Healthy Controls"
- **Contents**: 41 samples from Parkinson’s patients, 40 from healthy controls
- **Data Type**: Isolated, prolonged vowel sounds (.wav)
- **Use**: Acoustic and prosodic feature extraction (e.g., Jitter, Shimmer, HNR)

---

### 2. Spectrogram-Based Approach
- **Derived From**: Same Figshare dataset used above
- **Use**: Mel spectrograms and log-Mel spectrograms generated from audio
- **Input to**: CNN-based image models (EfficientNet, ResNet, etc.)

---

### 3. Speech-to-Text + BERT Approach
- **Dataset Sources**:
  - **Healthy Samples**: Mozilla Common Voice (English, clean recordings)
  - **Parkinson’s Samples**: SJTU Parkinson’s Speech Dataset (downloaded from GitHub)
- **Data Type**: Full speech sentences
- **Use**: Transcriptions were **generated using OpenAI Whisper ASR**, then used as input for fine-tuned BERT-based NLP models.

---

### ⚠️ Note:
Due to licensing restrictions and file size limits, **full datasets are not included in this repository**.  
You can download them from the original sources:

- Figshare: [https://figshare.com/articles/dataset/Voice_Samples_for_Patients_with_Parkinson_s_Disease_and_Healthy_Controls/23849127](https://figshare.com/articles/dataset/Voice_Samples_for_Patients_with_Parkinson_s_Disease_and_Healthy_Controls/23849127)
- Mozilla Common Voice: [https://commonvoice.mozilla.org/en/datasets](https://commonvoice.mozilla.org/en/datasets)
- SJTU Dataset GitHub: [https://github.com/SJTU-YONGFU-RESEARCH-GRP/Parkinson-Patient-Speech-Dataset](https://github.com/SJTU-YONGFU-RESEARCH-GRP/Parkinson-Patient-Speech-Dataset)

---

### 📁 Included in this folder:
- `samples_numerical/`: A few example `.wav` files from the Figshare dataset
- `samples_text/`: A few `.wav` files used for transcription-based BERT models
- `metadata_numerical.csv`: Sample metadata for vowel-based audio (used in numerical/spectrogram branches)
- `transcriptions.csv`: Sample transcriptions generated from `.wav` files using Whisper ASR
