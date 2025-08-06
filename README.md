This project was proudly presented at the Deloitte Capstone Program 2025, where it addressed the pressing challenge of synthetic media threats in corporate and social contexts.

🧠 End-to-End Architecture Overview
Our pipeline follows a structured, research-driven approach:

📁 1. Frame Extraction & Preprocessing
🎥 Extracted frames from benchmark datasets (FakeAVCeleb, FakeAV Celeb etc.)

🔍 Resized to 256×256 pixels

⚙️ Applied CLAHE (Contrast Limited Adaptive Histogram Equalization)

🔄 Followed by Data Augmentation to generate:

100K real frames and
100K fake frames


🌊 2. Dual-Branch Wavelet Transformation

🔀 The augmented frames are passed into two independent branches:

Branch 1: Curvelet Wavelet Transformation

Performed curvelet decomposition

Removed redundant columns

Standardized features

Exported as a .csv file

Branch 2: Shearlet Wavelet Transformation

Applied shearlet transform

Used Landmark Isomap for feature reduction

Standardized features

Exported as a .csv file


🔗 3. Hybrid Cross Wavelet Fusion
Combined both standardized CSVs to enhance frequency-based features

Fusion amplifies discriminative components captured by different wavelet bases.


🧠 4. Classification using MLP
Fed fused features into a Multilayer Perceptron with architecture:

Dense Layers: 256 → 128 → 64

Output: Real / Fake classification


🏆 Presented at Deloitte
We demonstrated the model’s effectiveness in front of Deloitte experts by:

Simulating real-world deepfake attack vectors

Showcasing frame-level detection accuracy

Emphasizing robustness through wavelet fusion

Discussing enterprise-ready deployment via API and SDK


📈 Results & Evaluation
💯 Balanced accuracy on large-scale datasets

🎯 Precision-Recall tuning for minimizing false positives

🔒 Strong generalization against low-quality compressed deepfakes


📂 Explore the Codebase
frame_extraction/ – Frame capture & CLAHE + augmentation logic

wavelet_transforms/ – Curvelet and Shearlet transformation pipelines

feature_fusion/ – Hybrid Cross Wavelet Fusion

ml_model/ – MLP architecture and training

deployment/ – API & SDK setup (Flask based)


🔐 Securing authenticity in a synthetic world — one frame at a time.
⭐ Star this repo if you find it useful
🤝 Open for collaboration!
