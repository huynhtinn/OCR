
# 🧾 End-to-End Vietnamese Text Recognition (OCR)

<p align="center">
  <img src="https://i.imgur.com/your-ocr-demo.gif" alt="OCR Project Demo" width="800"/>
  <!-- Gợi ý: ảnh GIF mô tả từ ảnh gốc → phát hiện → nhận dạng text -->
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Framework-PyTorch-orange" alt="PyTorch">
  <img src="https://img.shields.io/badge/Detector-PaddleOCR-red" alt="PaddleOCR">
</p>

---

## 🧠 Overview

This project presents an end-to-end OCR system specifically designed for **Vietnamese scene text recognition**. It processes the **MC_OCR dataset** and implements a two-stage architecture:

- **Text Detection** using **PaddleOCR**
- **Text Recognition** using a custom **CNN + Transformer** model built in **PyTorch**

---

## ✨ Key Features

- ✅ **Two-Stage OCR Pipeline**: separates detection from recognition for modularity and accuracy  
- 🧠 **Custom Recognition Model**: CNN Encoder + Transformer Decoder  
- 📦 **Vietnamese Dataset Support**: parses and trains on MC_OCR (polygon-based labels)  
- 📊 **Evaluation**: uses Character Error Rate (CER) & Sequence Accuracy  
- 🎯 **Visual Output**: draws bounding boxes and predicted text on original image

---

## 🧱 Model Architecture

### 🔹 Encoder – CNN

- Inspired by CRNN
- Converts text-line images into sequential visual features

### 🔹 Decoder – Transformer

- Uses self-attention and cross-attention
- Autoregressively generates characters one by one

---

## 🚀 How to Run

This project is implemented entirely in a single Google Colab notebook.

### 🔧 Prerequisites

- Google Account with access to Google Drive
- Upload MC_OCR dataset to your Drive
- Update paths in the notebook:

```python
DRIVE_PATH = '/content/drive/MyDrive/DeepLearning/Final/'
TRAIN_CSV_PATH = DRIVE_PATH + 'Dataset/mcocr_public/mcocr_train_data/mcocr_train_df.csv'
TRAIN_IMG_DIR = DRIVE_PATH + 'Dataset/mcocr_public/mcocr_train_data/train_images/'
````

### 📋 Steps

1. **Open the notebook** in Google Colab
2. **Connect to GPU runtime**
3. **Mount Drive** and install required libraries
4. **Run the notebook sequentially**:

   * 📊 Preprocessing: parses MC\_OCR CSV with polygon annotations
   * 🧠 Model: defines CNN + Transformer OCRModel
   * 🔁 Training: saves best model based on validation CER
   * 🧪 Evaluation: computes final CER & Sequence Accuracy
   * 🖼️ Inference: visualizes prediction on sample images

---

## 📊 Evaluation Results

| Metric                     | Score        |
| -------------------------- | ------------ |
| Test Loss                  |    0.4042    |
| Character Error Rate (CER) |    0.1502    |
| Sequence Accuracy          |    59.03%    |

<p align="center">
  <img src="https://cdn.discordapp.com/attachments/1242824807456964762/1387845524958216212/tai_xuong.png?ex=685ed35e&is=685d81de&hm=dad41c83febc8d054b0fcbbc73dcf4b0b278bf887ce8b0b573773b820efdbcd5&" alt="Training Chart" width="800"/>
</p>

---


## 🎓 Credits

This project was developed by me as part of the **Deep Learning final project** at **Ton Duc Thang University**.

📬 Contact: [tinphamwork@gmail.com](mailto:tinphamwork@gmail.com)
🔗 Linkedin: [linkedin/phtin](https://www.linkedin.com/in/phtin/)

---





