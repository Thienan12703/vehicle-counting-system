### 🚗 Vehicle Counting System (YOLO-based)
##📋 Project Overview

This project develops a comprehensive pipeline for training, evaluating, and performing inference using YOLO-based models for vehicle detection and counting. The models are trained on the VisDrone dataset and extensively evaluated on the VisDrone_test dataset.

The system also provides an interactive web-based dashboard using Streamlit for real-time inference and model management.

## 🎯 Key Features
Vehicle Detection & Counting: Automatically detects and counts multiple vehicle types using YOLO models
SAHI Integration: Improves small object detection performance through slicing-based inference
Advanced Evaluation: Computes AP metrics and generates confusion matrices for in-depth model analysis
Streamlit Dashboard: Interactive interface for model selection, inference on images/videos, and visualization
Flexible Class Mapping: Supports dynamic label filtering and class remapping for VisDrone dataset
🏗 Project Structure
```text
vehicle-counting-system/
├── streamlit_app.py          # Streamlit dashboard for inference & model management
├── train.py                  # YOLO model training script
├── inference_utils.py        # Utilities (annotation parsing, IoU calculation, etc.)
├── split_dataset.py          # Dataset splitting tool
├── test/
│   ├── evaluate_models.py    # Model evaluation script
│   ├── model/                # Tested model weights (e.g., yolo26m, yolo26m-p2)
│   └── Visdrone_test/        # Test dataset with YOLO-format labels
├── models/                   # Default directory for model weights (.pt)
└── data.yaml                 # Dataset configuration
```
## 🚀 Installation
1. Clone the repository
git clone https://github.com/yourusername/vehicle-counting-system.git
cd vehicle-counting-system
2. Create Conda environment
conda create -n cvenv python=3.9 -y
conda activate cvenv
3. Install dependencies
Install PyTorch (example for CUDA 12.x)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
Install required packages
pip install -r requirements.txt
## 🎮 Usage
1. Launch Streamlit Dashboard
conda run -n cvenv streamlit run streamlit_app.py

## 👉 Open browser at: http://localhost:8501

2. Evaluate Models on VisDrone_test
conda run -n cvenv python test/evaluate_models.py --conf 0.5 --iou 0.5
3. Train Model
conda run -n cvenv python train.py
4. Split Dataset
conda run -n cvenv python split_dataset.py
## 📊 Results & Insights
YOLO26m (960 resolution): Strong performance in class-specific detection (car, bus, truck), capturing full object context effectively
YOLO26m-P2 (768 resolution): Excellent performance on small object detection due to P2 detection head, though limited in class diversity
SAHI Impact: Significantly improves detection accuracy for small and densely packed vehicles
Evaluation Consistency: Direct evaluation on VisDrone_test preserves dataset distribution and ensures reliable mAP measurement

## 💡 Technical Highlights
Addressed challenges of dense object detection and occlusion in aerial imagery
Implemented SAHI (Slicing Aided Hyper Inference) to enhance small object detection
Optimized Non-Maximum Suppression (NMS) for crowded traffic scenarios
Designed evaluation pipeline for accurate AP/mAP computation with YOLO-format annotations

## 🤝 Contributing
Fork the repository
Create a new branch (git checkout -b feature/AmazingFeature)
Commit your changes
Push to the branch
Open a Pull Request
## 📞 Contact
# Author: Nguyen Thien An
# GitHub: (https://github.com/Thienan12703?tab=repositories)
# Project Link: https://github.com/yourusername/vehicle-counting-system

