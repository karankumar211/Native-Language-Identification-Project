# Native Language Identification of Indian English Speakers Using HuBERT

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Framework](https://img.shields.io/badge/Framework-PyTorch%20%7C%20HuggingFace-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview

This project develops an automated system to identify the **native language (L1)** of Indian English speakers based on their accent. It leverages both traditional signal processing (**MFCCs**) and modern Self-Supervised Learning (**HuBERT**) to classify speakers into regional groups (e.g., Malayalam, Tamil, Hindi, Kannada, Telugu).

The project culminates in a real-world **"Accent-Aware Cuisine Recommendation System"**, which suggests regional dishes based on the detected accent of the user.

## 🚀 Key Features & Tasks

### **Task 1: Native Language Identification Model**
* **Objective:** Build and compare classifiers for Indian accents.
* **Methods:**
    * **Baseline:** Support Vector Machine (SVM) trained on **MFCC** features.
    * **Deep Learning:** SVM trained on **HuBERT** (Hidden-Unit BERT) embeddings.
    * **Layer-wise Analysis:** Investigated all 12 transformer layers of HuBERT to find the best layer for accent detection.
* **Result:** Achieved **>99% accuracy** on the sentence-level dataset.

### **Task 2: Generalization Across Age Groups**
* **Objective:** Test if the model (trained on Indian Adults) generalizes to Child speech.
* **Experiment:** Evaluated the adult model on the **SpeechOcean762** dataset (Mandarin children).
* **Finding:** The model demonstrated significant domain mismatch, proving that accent identification models are sensitive to vocal tract differences (pitch/formants) between adults and children.

### **Task 3: Linguistic Level Analysis (Word vs. Sentence)**
* **Objective:** Compare accent detection performance on full sentences versus isolated words.
* **Method:** Used **CTC-Segmentation** (Wav2Vec2 ASR) to force-align audio and extract **43,000+** word-level samples.
* **Finding:** Sentence-level classification (99.5%) significantly outperforms word-level classification (94.1%), highlighting the importance of prosody and context.

### **Task 4: Cuisine Recommendation Application**
* **Objective:** Demonstrate a real-world use case.
* **Tech Stack:** Built with **Gradio** for the web interface.
* **Functionality:** Records user audio → Detects Accent → Recommends regional food (e.g., *Kerala Accent → Appam, Puttu*).

---

## 📂 Repository Structure

| File | Description |
| :--- | :--- |
| `Task1.ipynb` | **Model Development:** Feature extraction (MFCC/HuBERT), Model Training, and Layer-wise Analysis. |
| `Task2.ipynb` | **Age Generalization:** Testing the adult model on child speech data. |
| `Task3.ipynb` | **Linguistic Analysis:** Word-level segmentation, feature extraction, and comparison. |
| `Task4.ipynb` | **Application:** The Gradio-based "Cuisine Recommendation" web app. |
| `requirements.txt` | List of Python dependencies required to run the project. |
| `README.md` | Project documentation (this file). |

---

## 🛠️ Installation & Usage

### **Prerequisites**
This project requires Python 3.8+ and a GPU environment (Google Colab T4 recommended).

### **1. Clone the Repository**
```bash
git clone [https://github.com/yourusername/Native-Language-Identification-Project.git](https://github.com/yourusername/Native-Language-Identification-Project.git)
cd Native-Language-Identification-Project
