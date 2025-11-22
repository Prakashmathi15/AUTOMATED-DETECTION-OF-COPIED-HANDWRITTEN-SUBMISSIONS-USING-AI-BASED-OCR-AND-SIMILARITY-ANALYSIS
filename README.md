# 📝 Automated Detection of Copied Handwritten Submissions-TEAM 164 🚀

![Python](https://img.shields.io/badge/Python-3.9-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-ee4c2c.svg)
![Transformers](https://img.shields.io/badge/Hugging%20Face-TrOCR-yellow.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-Image%20Processing-green.svg)

## 📌 Overview

Academic integrity is crucial, but traditional plagiarism checkers (like Turnitin) cannot read **handwritten** assignments. This project bridges that gap.

This is an **End-to-End Automated Pipeline** that ingests scanned PDF submissions, preprocesses them using Computer Vision, extracts text using the state-of-the-art **TrOCR (Transformer-based OCR)** model, and algorithmically compares every student's work against every other student to detect verbatim copying.

## 🚀 Key Features

* **📄 Batch Processing:** Automatically converts and processes folders full of PDF submissions.
* **🖼️ Advanced Preprocessing:** Uses OpenCV for Denoising and Adaptive Thresholding to clean noisy scans.
* **🤖 AI-Powered OCR:** Utilizes `microsoft/trocr-large-handwritten` for superior accuracy on diverse handwriting styles.
* **🔍 Pairwise Comparison:** Compares every document against every other document ($N^2$ complexity) to ensure no copy goes unnoticed.
* **📊 Visual Reports:** Generates a similarity matrix heatmap and a detailed text report flagging suspicious pairs (Threshold > 75%).

---

## 🛠️ System Architecture

The pipeline follows a linear flow:

1.  **Input:** Batch of Student PDFs.
2.  **Conversion:** PDF $\rightarrow$ High-Res Images.
3.  **Preprocessing:** Grayscale $\rightarrow$ Bilateral Filter $\rightarrow$ Adaptive Thresholding.
4.  **Inference:** TrOCR Encoder-Decoder Model extracts text.
5.  **Normalization:** Lowercase conversion and whitespace removal.
6.  **Analysis:** Sequence Matching (Gestalt Pattern Matching).
7.  **Output:** Plagiarism Report & Heatmap.

---

## ⚙️ Installation

### Prerequisites
* Python 3.8+
* **Poppler** (Required for `pdf2image`):
    * *Windows:* Download binary and add to PATH.
    * *Linux:* `sudo apt-get install poppler-utils`
    * *Mac:* `brew install poppler`

### Install Dependencies
Run the following command to install the required Python libraries:

```bash
pip install torch torchvision torchaudio
pip install transformers
pip install opencv-python
pip install pdf2image
pip install scikit-learn
pip install seaborn
pip install matplotlib
pip install pillow
```

## 💻 UsageClone the Repository:
Bash git clone
```
[https://github.com/yourusername/handwritten-plagiarism-detector.git](https://github.com/yourusername/handwritten-plagiarism-detector.git)
cd handwritten-plagiarism-detector
```
## Prepare Input:     
Place all student PDF files in the student_submissions/ directory.
## Run the Pipeline:  
Bashpython main.py   

## View Results:
Check the console for the text report. 
Open similarity_matrix.png to see the heatmap.
Check logs/plagiarism_report.txt for the detailed breakdown.
## 📸 Sample Outputs1. 
## Preprocessing Pipeline

   ![4](https://github.com/user-attachments/assets/0993d143-fb60-47c7-b8b8-499cf96cddbb)     
    
   ![3](https://github.com/user-attachments/assets/e8a75459-2c29-48c6-8ea7-c68caad0cc88)

   ![1](https://github.com/user-attachments/assets/daf9296f-6a29-4696-a015-8c93ec352969)


## 🧠 Algorithms Used  
ComponentAlgorithm/ModelPurposeOCRTrOCR (Vision Transformer)End-to-end text recognition from images.          
PreprocessingAdaptive Gaussian ThresholdingHandling uneven lighting and shadows in scans.                
ComparisonSequenceMatcherFinding longest contiguous matching subsequences.              
## 🔮 Future Scope

Semantic Analysis: Integrating BERT/RoBERTa to detect paraphrased content (copied ideas, not just words).   

Web Interface: Developing a React/Flask web app for easy drag-and-drop usage.          
Internet Search: Extending the check to compare against online sources (Wikipedia, Chegg) via APIs.
## 👥 Contributors
  1.) PRAKASH M - CSE(CS)              
  2.) THANJIYAPPAN K - AI&ML          
  3.) SANJAY K - CSE             
## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
