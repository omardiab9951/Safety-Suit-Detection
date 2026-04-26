<div align="center">

<img src="https://img.shields.io/badge/Safety%20AI-Industrial%20Vision-FF6600?style=for-the-badge" />
<img src="https://img.shields.io/badge/Model-YOLOv8-00C4CC?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Task-Object%20Detection-blueviolet?style=for-the-badge" />
<img src="https://img.shields.io/badge/Domain-Computer%20Vision-228B22?style=for-the-badge" />

# 🦺 Safety Suit Detection Model
### Real-Time PPE Compliance Detection for Industrial Environments

*A production-ready deep learning pipeline that detects whether workers are wearing their safety suits — enforcing protection before accidents occur.*

[![Author](https://img.shields.io/badge/Author-Omar%20Diab-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/omar9951)
[![GitHub](https://img.shields.io/badge/GitHub-omardiab9951-181717?style=flat-square&logo=github)](https://github.com/omardiab9951)

</div>

---

## 🔍 Overview

In high-risk industrial environments — construction sites, factories, chemical plants, and oil & gas facilities — failing to wear a safety suit is one of the leading causes of severe workplace injuries and skyrocketing medical insurance costs. Manual PPE inspection is inconsistent and impossible to scale.

This project delivers a **real-time computer vision system** that automatically detects whether workers are wearing their safety suits using a fine-tuned **YOLOv8** object detection model. Designed to integrate seamlessly with existing CCTV infrastructure, it provides continuous, automated compliance monitoring without relying on human oversight.

### 💡 The Problem
- Workplace injuries from inadequate PPE cost employers billions in insurance claims and legal liability every year
- Manual safety checks are slow, subjective, and reactive — they catch violations *after* the fact
- High-turnover industrial environments make consistent enforcement extremely difficult

### ✅ The Solution
An always-on, camera-based AI system that:
- Detects **safety_suit** vs **no_safety_suit** in real time on live video feeds
- Flags non-compliant workers instantly for supervisor intervention
- Creates a continuous, timestamped compliance record — replacing manual audits with automated accountability

---

## 🏗️ Model Architecture

| Component | Details |
|---|---|
| **Base Architecture** | YOLOv8 |
| **Task** | Object Detection (2-class) |
| **Classes** | `safety_suit` · `no_safety_suit` |
| **Framework** | PyTorch (via Ultralytics) |
| **Input Resolution** | 640 × 640 |
| **Training Platform** | Kaggle (Tesla T4 GPU) |

---

## 📦 Dataset

- **Collection:** Manually collected by the author — images sourced and curated specifically for safety suit detection in industrial contexts
- **Labeling:** Annotated and labeled using **Roboflow**, with bounding boxes drawn around workers and their PPE compliance status
- **Classes:** 2 — `safety_suit` (compliant), `no_safety_suit` (non-compliant)
- **Format:** YOLO-format bounding box annotations
- **Split:** Train / validation split configured via Roboflow's export pipeline

---

## 🛠️ Installation & Usage

### Prerequisites
```bash
pip install ultralytics
pip install opencv-python
```

### Clone the Repository
```bash
git clone https://github.com/omardiab9951/Safety-Suit-Detection.git
cd Safety-Suit-Detection
```

### Run Inference on an Image
```python
from ultralytics import YOLO

model = YOLO("weights/best.pt")
results = model.predict(source="your_image.jpg", conf=0.5, save=True)
results[0].show()
```

### Run Real-Time Webcam Detection
```python
from ultralytics import YOLO

model = YOLO("weights/best.pt")
model.predict(source=0, conf=0.5, show=True)  # source=0 for webcam
```

### Run on Video File
```python
from ultralytics import YOLO

model = YOLO("weights/best.pt")
model.predict(source="site_footage.mp4", conf=0.5, save=True)
```

---

## 🎯 Target Use Cases

| Environment | Application |
|---|---|
| 🏗️ Construction Sites | Full-body PPE compliance monitoring across large sites |
| 🏭 Manufacturing Plants | Assembly line and floor worker safety enforcement |
| ⚗️ Chemical & Oil Facilities | High-risk zone access control and hazard suit verification |
| ⚡ Electrical Utilities | Protective gear confirmation before high-voltage work |
| 🚧 Road & Infrastructure Works | Contractor compliance on public-facing job sites |

---

## 📈 Why This Matters

> According to the International Labour Organization, **2.3 million workers** die annually from work-related accidents and diseases. A significant proportion of non-fatal injuries involve inadequate or absent PPE — costing employers hundreds of billions in medical insurance, downtime, and legal exposure.

Automated safety suit detection shifts the paradigm from **reactive incident response** to **proactive, real-time prevention** — at a fraction of the cost of dedicated safety personnel and with zero fatigue or blind spots.

---

## 🔭 Roadmap & Future Work

- [ ] Expand to full PPE suite detection: helmets, gloves, safety goggles, high-vis vests
- [ ] Live alert integration: Slack, SMS, and on-site alarm systems
- [ ] Edge deployment: ONNX / TensorRT export for NVIDIA Jetson and Raspberry Pi
- [ ] Multi-camera tracking with worker ID association across frames
- [ ] Combined pipeline with the [Goggles Detection Model](https://github.com/omardiab9951/Googles-Detection-Model) for unified PPE compliance

---

## 👤 Author

**Omar Diab**
Data Science & AI Student — ElSewedy University of Technology, Polytechnic of Egypt

[![LinkedIn](https://img.shields.io/badge/LinkedIn-omar9951-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/omar9951)
[![GitHub](https://img.shields.io/badge/GitHub-omardiab9951-181717?style=flat-square&logo=github)](https://github.com/omardiab9951)
[![Email](https://img.shields.io/badge/Email-omarkamaldiab9951@gmail.com-EA4335?style=flat-square&logo=gmail)](mailto:omarkamaldiab9951@gmail.com)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

<div align="center">

*Built with purpose — because workplace safety is not optional.*

⭐ If this project helped you, consider giving it a star!

</div>
