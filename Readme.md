# Temporal Deepfake Detection using Optical Flow and Facial Dynamics

### Author: Sunny  
### Date: 20/04/2025

---

##  Overview

This project presents an advanced approach to **Deepfake Detection** by integrating **temporal modeling** using **optical flow** and **facial movement analysis over time**. It is designed to identify subtle temporal inconsistencies across video frames, which are often overlooked by traditional deepfake detectors that focus solely on spatial features.

([Download Dataset](https://drive.google.com/file/d/19bdkVaWD0_TDG3XtSUfXhptCjpgi_8mu/view?usp=drive_link))

It builds upon previous work ([DeepFakeDetection_-DFDC-](https://github.com/SAARKS-BH/DeepFakeDetection_-DFDC-)), enhancing detection performance through dynamic facial behavior modeling.

---

##  Why This Project Matters

With the rise of generative AI, deepfakes are increasingly realistic and harder to catch using static image-based models. This has serious implications for:

-  Media authenticity  
-  Political misinformation  
-  Legal evidence validation  
-  Identity fraud and impersonation

This model analyzes **facial motion over time**, adding a crucial dimension to improve detection accuracy — **temporal coherence**.

---

##  Objective

To develop a deepfake detection prototype that:
- Uses **optical flow** to extract motion vectors between frames
- Models **temporal dependencies** in facial expressions and movements
- Outperforms static-only CNN-based methods

---

##  Key Features

-  **Optical Flow Integration**: Captures inter-frame motion, highlighting unnatural facial transitions.
-  **Temporal Attention Modeling**: Detects inconsistencies in eye movements, blinking, lip synchronization, etc.
-  **Visual Output Support**: Generates annotated `.png` files to highlight temporal anomalies.
-  **Modular Jupyter Notebook Workflow**: Easy to modify, interpret, and retrain.

---

## 🧪 Methodology

### 1. Data Preparation
- Frames are extracted from videos and converted to grayscale.
- Optical flow (Farneback method) is used to calculate frame-to-frame motion.
- Each video is converted into a temporal sequence of flow maps.

### 2. Model Architecture
- Input: Sequences of optical flow frames
- Components:
  - `TimeDistributed` Conv2D layers → spatial feature extractor
  - LSTM → models sequential dependencies in facial movements
  - Dense layer → binary classification (Real vs Fake)

### 3. Training & Evaluation
- Loss function: Binary Crossentropy
- Optimizer: Adam
- Evaluation Metrics: Accuracy and loss on validation/test splits
- Includes **early stopping** to prevent overfitting

---

##  Difference from Previous Work

> 🔗 Reference: [DeepFakeDetection_-DFDC-](https://github.com/SAARKS-BH/DeepFakeDetection_-DFDC-)

| Feature              | Previous Project                     | This Project                                      |
|----------------------|--------------------------------------|---------------------------------------------------|
| Frame Handling       | Single-frame CNN                     | Multi-frame sequence modeling                     |
| Temporal Awareness   | None                                 | Optical Flow + Time-dependent Feature Tracking |
| Dataset              | DFDC                                 | Video-based sequences                             |
| Detection Focus      | Visual artifacts                     | Motion inconsistencies                            |
| Real-World Robustness| Moderate                             | High                                              |

---

##  Industry Potential

This detection system is highly applicable to:

-  **Forensics** – Authenticity checks in legal scenarios
-  **Social Media Platforms** – Flagging synthetic videos in real-time
-  **News Agencies** – Validating citizen journalism footage
-  **Digital KYC & Banking** – Preventing facial identity fraud

Temporal modeling exposes inconsistencies in facial dynamics — a weakness still found in even the best AI-generated fakes.

---

##  How to Use

### Option 1: Run via Jupyter Notebook
1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/Temporal-Deepfake-Detection
   cd Temporal-Deepfake-Detection
