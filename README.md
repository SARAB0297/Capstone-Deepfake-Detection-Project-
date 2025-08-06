# 🛡️ DeepFake Detection using Hybrid Wavelet Fusion

This project was proudly presented at the **Deloitte Capstone Program 2025**, where it addressed the pressing challenge of synthetic media threats in corporate and social contexts.

---

## 🧠 End-to-End Architecture Overview

Our pipeline follows a structured, research-driven approach:

### 📁 1. Frame Extraction & Preprocessing

- 🎥 Extracted frames from benchmark datasets (FakeAVCeleb, CelebDF etc.)
- 🔍 Resized to 256×256 pixels
- ⚙️ Applied CLAHE (Contrast Limited Adaptive Histogram Equalization)
- 🔄 Followed by Data Augmentation to generate:
  - `100K real frames`
  - `100K fake frames`

---

### 🌊 2. Dual-Branch Wavelet Transformation

Augmented frames were then passed through shearlet and curvelet pipelines to detect features.

#### 📐 Branch 1: Curvelet Wavelet Transformation

- Performed curvelet decomposition  
- Removed redundant columns  
- Standardized features  
- Exported as `.csv` file  

#### 🧩 Branch 2: Shearlet Wavelet Transformation

- Applied shearlet transform  
- Feature reduction using **Landmark Isomap**  
- Standardized features  
- Exported as `.csv` file  

---

### 🔗 3. Hybrid Cross Wavelet Fusion

- Combined both standardized `.csv` files  
- Fusion amplified frequency-domain discriminative features  
- Enhanced model robustness against compression artifacts

---

### 🧠 4. Classification using MLP

- Used **Multilayer Perceptron (MLP)**  
- Architecture:  
  `Dense Layers: 256 → 128 → 64`  
- Output: Real / Fake classification

---

## 🏆 Presented at Deloitte

We demonstrated the model’s effectiveness by:

- Simulating real-world deepfake attack vectors  
- Frame-level detection accuracy  
- Emphasizing robustness through hybrid wavelet fusion  
- Discussing enterprise-ready deployment via **API and SDK**

---

## 📈 Results & Evaluation

- 💯 High balanced accuracy on large-scale datasets  
- 🎯 Precision-Recall tuning for minimizing **false positives**  
- 🔒 Generalizes well even against low-quality deepfakes

---

## 📂 Explore the Codebase

| Folder             | Description                                |
|--------------------|--------------------------------------------|
| `frame_extraction/` | CLAHE + Data Augmentation logic           |
| `wavelet_transforms/` | Curvelet and Shearlet wavelet pipelines |
| `feature_fusion/`  | Hybrid Cross Wavelet Fusion logic          |
| `ml_model/`        | MLP architecture & training                |

---

🔐 **Securing authenticity in a synthetic world — one frame at a time.**

⭐ *Star this repo if you find it useful*  
🤝 *Open for collaboration!*
