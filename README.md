# ArSL-3D: 3D Alphanumeric Recognition for Arabic Sign Language

An educational and translation application designed to bridge the communication gap for the deaf and hard-of-hearing community in Egypt. This project features a robust 3D hand pose recognition system for Arabic Sign Language (ArSL) that supports letters, numbers, and selected words, integrated into a real-time mobile translation platform.

## 🌟 Key Features
* **3D Hand Pose Recognition:** Uses parametric 3D representations to overcome depth ambiguity and self-occlusion common in 2D methods.
* **Text-to-Sign Translation:** Features an animated avatar that translates input text into Egyptian Sign Language gestures.
* **Real-Time Performance:** High-speed inference reaching over 800 FPS, making it suitable for deployment on standard hardware.
* **Comprehensive Vocabulary:** Supports 42 distinct classes including 31 alphabet letters and 11 numerical digits.

## 🛠️ Tech Stack
* **Core:** Python, OpenCV, Scikit-learn
* **Computer Vision:** YOLOv8, WiLoR (Wild Look-at-the-Hand), MANO Model
* **Machine Learning:** MLP (Multi-Layer Perceptron), Random Forest, PCA (Principal Component Analysis)
* **Backend & Mobile:** FastAPI, Flutter

## 📐 System Architecture
The recognition module follows a specialized pipeline:
1. **Localization:** A YOLOv8-based detector isolates the hand region to ensure scale consistency.
2. **3D Reconstruction:** The WiLoR framework regresses full 3D mesh and joint articulations from a single RGB image.
3. **Feature Engineering:** Extraction of a 151-dimensional hybrid vector including global orientation (SO(3) rotation matrices) and scale-invariant geometric distance ratios.
4. **Classification:** An optimized MLP head classifies the 3D features into sign categories.

## 🚀 Performance
The system achieves state-of-the-art accuracy and speed:

| Task | Model | Accuracy | Inference Speed |
| :--- | :--- | :--- | :--- |
| **Alphabetical** | MLP | 95.72% | ~837 FPS |
| **Numerical** | MLP | 88.7% | ~1411 FPS |

## 👨‍💻 My Contribution
As the developer of the **Recognition Module**, I was responsible for:
* Implementing the **WiLoR pipeline** for 3D hand pose estimation using the **MANO model**.
* Designing the **151-dimensional feature vector** and performing **PCA** for dimensionality reduction.
* Conducting **feature importance analysis** to identify critical keypoints (e.g., thumb-to-pinky separation).
* Training and optimizing the **MLP classifier** with L2 regularization and early stopping.
* Building the **FastAPI backend** to provide real-time inference to the **Flutter app**.

## 📚 Acknowledgments
This research was based on the paper: *"3D Alphanumeric Recognition in Arabic Sign Language Using WiLoR-Based 3D Hand Pose Features"*.