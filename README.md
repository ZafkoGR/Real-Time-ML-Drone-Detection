# 🚁 Real-Time Drone Detection Tool (YOLOv10s)

A deep-learning system that identifies drones in live camera feeds, leveraging the small yet powerful **YOLOv10s** architecture for sub-15 ms inference on GPU or edge devices.

---

## 📘 Project Background  

This tool constitutes **Chapter 5.2** of my Master’s thesis, *Practical AI in Cyberwarfare and Cybersecurity*, and is **officially included** in the submitted document.

**Author**: Konstantinos Zafeiropoulos (Student ID 20390293)  
**Institution**: University of West Attica – Faculty of Engineering, Department of Informatics and Computer Engineering  

> 📚 The full thesis (including this tool) will appear in the institutional repository **«Πολυνόη» (Polynoe)** and on **Google Scholar** by **September 2025**.

---

## 1️⃣ Why AI is Needed  

- Drones are **small, fast-moving, variably shaped**, and appear under diverse lighting.  
- Traditional rules or background subtraction fail to generalize.  
- Deep CNNs learn the **fine-grained spatial patterns** required for reliable, real-time recognition.

---

## 2️⃣ Can This Be Done Without AI?  

Rule-based or classical vision approaches:  
- Break under occlusion, low light, or novel drone designs.  
- Cannot scale to outdoor, unconstrained scenarios.  

✅ **AI (deep learning) is essential** for practical, scalable detection.

---

## 3️⃣ AI Algorithm & Architecture  

### ✅ Model: **YOLOv10s**  
- ~8 M parameters, ~24 GFLOPs  
- **Backbone**: Conv, SCDown, C2f, C2fCIB  
- **Neck**: SPPF + PSA for multi-scale fusion  
- **Head**: Anchor-free `v10Detect` (bbox + class)  

### 🔄 Workflow  
1. **Input**: 640 × 640 image frame  
2. **YOLOv10s inference** → bounding boxes + confidence  
3. **Output**: Drone coordinates & confidence in < 15 ms (Tesla P100)  

---

## 4️⃣ AI Subcategory  

✅ **Computer Vision** → **Object Detection** (Supervised Deep Learning)

---

## 5️⃣ Purpose & Social Impact  

- **Airspace Security**: Block rogue drones at airports & events  
- **Disaster Response**: Track aid-delivery or survey drones  
- **Critical Infrastructure**: Early warning for hostile UAVs  
- **Smart Cities**: Monitor urban drone traffic  

Automated detection = faster response, safer skies.

---

## 6️⃣ Dataset Overview  

| Split     | Images | Labels | Classes |
|-----------|--------|--------|---------|
| Train     | 1 089  | YOLO txt | `drone` (0) |
| Validation|   135  | YOLO txt | `drone` (0) |

**Label format**: `<class_id> <x_center> <y_center> <width> <height>` (normalized).

---

## 📊 Performance Snapshot  

- **mAP@0.5**: 0.88  
- **Precision**: 0.819  
- **Recall**: 0.841  
- **mAP@0.5:0.95**: 0.579  
- Real-world test: detected 2 drones in a military image (0.81, 0.68 conf.) in 12 ms.

---

## 📄 License  

**All Rights Reserved**  
© 2025 Konstantinos Zafeiropoulos

This work is protected by copyright law and international treaties.

No part of this repository, including code, data, models, documentation, or any other associated materials (collectively, the "Work"), may be copied, reproduced, modified, published, uploaded, posted, transmitted, or distributed in any form or by any means, without the prior written permission of the author, except for personal academic reference and citation.

You may not:
- Use this work for commercial purposes  
- Distribute copies or modified versions of this work  
- Use any part of this work to create derivative works, including research, software, or datasets, without explicit permission  
- Upload this work or its derivatives to other platforms (e.g., Kaggle, Hugging Face, or other GitHub repositories)

For academic citation, proper attribution must be given to:  
**Konstantinos Zafeiropoulos – University of West Attica, 2025**

This work is part of the author’s official Master’s thesis submission, which will be published in the institutional repository **«Πολυνόη»** and indexed on **Google Scholar** by **September 2025**.
