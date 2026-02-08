<div align="center">

# YOLOv8-ToolKit

### *A Comprehensive Utility Suite for YOLOv8 Development*

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-00FFFF.svg)](https://docs.ultralytics.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

*Streamline your YOLOv8 workflow with powerful preprocessing, training, and deployment tools*

[Features](#-features) • [Documentation](#-documentation)

</div>

---

## 📋 Overview

YOLOv8-ToolKit is a collection of utility scripts designed to simplify the entire YOLOv8 development pipeline—from data preparation and annotation to model training and real-time inference. Whether you're preprocessing datasets or deploying models, this toolkit has you covered.

---

## ✨ Features

<table>
<tr>
<td width="50%">

🖼️ **Data Preprocessing**
- Extract frames from videos
- Split datasets intelligently
- Combine multiple datasets

</td>
<td width="50%">

**AI-Powered Tools**
- Auto-annotation with existing models
- Real-time video streaming
- Coordinate capture utility

</td>
</tr>
</table>

---

## Quick Start

```bash
# Clone the repository
git clone https://github.com/TarunB1006/YoloV8-ToolKit.git
cd YoloV8-ToolKit

# Install dependencies
pip install ultralytics opencv-python
```

---

## 🛠️ Tools

### **Extract Images** → `extract_images.py`

Extract frames from video at custom intervals for dataset creation.

```python
# Configuration
video_path = "your_video.mp4"
frame_skip = 25  # Save 1 frame per second (for 25 FPS video)
```

> **Use Case:** Build your dataset by extracting frames from videos at specified intervals.

---

### **Data Split** → `data_split.py`

Split your dataset into training, validation, and testing sets according to YOLOv8 format.

```
📁 Dataset Structure
├── train/
│   ├── images/
│   └── labels/
├── val/
│   ├── images/
│   └── labels/
└── test/
    ├── images/
    └── labels/
```

> **Note:** Default format is `.jpg`. Modify Line 18 for other formats.

---

### **Data Combine** → `data_combine.py`

Merge multiple datasets into one unified dataset.

```
Dataset 1 + Dataset 2 + Dataset 3 → Combined Dataset
```

> **Use Case:** Combine datasets from multiple sources or annotators seamlessly.

---

### **Auto Annotate** → `auto_annotate.py`

Automatically annotate images using a pre-trained YOLOv8 model.

```python
# Required inputs
model_path = "your_model.pt"
images_folder = "path/to/images"
labels_folder = "path/to/labels"
```

> **Tip:** Verify auto-annotations manually using tools like [LabelImg](https://github.com/tzutalin/labelImg) for best results.

---

### **Stream Predictions** → `stream.py`

Visualize YOLOv8 predictions in real-time on video files.

```python
# Run live inference
python stream.py
```

> **Perfect for:** Testing model performance on real-world videos.

---

### **Configuration File** → `data.yaml`

Define training parameters for YOLOv8.

```yaml
# Example data.yaml
path: /path/to/dataset
train: train/images
val: val/images
nc: 3  # number of classes
names: ['class1', 'class2', 'class3']
```

📖 [YAML Configuration Guide](https://docs.ultralytics.com/modes/train/)

---

### **Training Notebook** → `training.ipynb`

Jupyter notebook with pre-configured hyperparameters to kickstart your training.

```python
# Basic training command
from ultralytics import YOLO
model = YOLO('yolov8n.pt')
model.train(data='data.yaml', epochs=100, imgsz=640)
```

📖 [Training Documentation](https://docs.ultralytics.com/modes/train/)

---

### **Capture Coordinates** → `capture_coordinates.py`

Interactive tool to capture coordinates from images using mouse clicks.

```
Click → Capture Points → Define ROI
```

> **Use Case:** Define regions of interest (ROI) for focused detection zones.

---

## 📖 Documentation

| Resource | Link |
|----------|------|
| YOLOv8 Official Docs | [docs.ultralytics.com](https://docs.ultralytics.com/) |
| Training Guide | [Training Mode](https://docs.ultralytics.com/modes/train/) |
| Prediction Guide | [Predict Mode](https://docs.ultralytics.com/modes/predict/) |
