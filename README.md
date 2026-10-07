# alpr_license_plate_detection
ITAI 1378 Midterm Blueprint - Automated License Plate Recognition System
# Automatic License Plate Recognition (ALPR) System

## Team Members
* **Edwin Marquez**
* **Chris Roy**
* **Unnati Shakya**
* **Njeh Ababio**

---

## Project Tier
**Tier 1 – Core**

This project focuses on building a robust end-to-end computer vision pipeline using proven pretrained models (YOLOv8 + EasyOCR) tailored for real-world automated tolling and security monitoring.

---

## Problem Statement
Manual vehicle logging in private parking facilities and toll booths causes congestion, increases operational labor costs, and introduces human error during peak traffic hours. Automated License Plate Recognition (ALPR) provides a reliable, scalable solution to process vehicle entries seamlessly in real time.

---

## Solution Overview
An automated computer vision system that captures vehicle images, detects and crops license plate regions using YOLOv8, extracts text using EasyOCR, and logs plate numbers into a structured database.

**Pipeline Flow:**  
`Input Image / Video Stream` ➔ `YOLOv8 Plate Detector` ➔ `Cropped Plate Region` ➔ `EasyOCR Text Reader` ➔ `Database Entry`

---

## Technical Approach
* **Computer Vision Task:** Object Detection + Optical Character Recognition (OCR)
* **Detection Model:** YOLOv8s (PyTorch)
* **OCR Engine:** EasyOCR (CRAFT Text Detection + CRNN Recognition)
* **Frameworks:** PyTorch, OpenCV, Pandas

---

## Data Plan
* **Source:** Roboflow Public License Plate Datasets / Kaggle ALPR Dataset
* **Dataset Size:** ~2,500 annotated images
* **Splits:** 70% Training, 15% Validation, 15% Testing
* **Labels:** Bounding Box coordinates for `license_plate`

---

## Success Metrics
* **Primary Metric:** Object Detection mAP@50 ≥ 90%
* **Secondary Metric:** Inference latency ≤ 50ms per image; OCR character recognition accuracy ≥ 88%

---

## Milestone Plan

| Phase | Goal | Milestone | 16-Week Term | 10-Week Term |
|---|---|---|---|---|
| **1. Blueprint** | Plan approved | Midterm submitted | Week 10 | Week 5 |
| **2. First Working Demo** | Pretrained model runs end-to-end on sample images | Pipeline functional | Week 11 | Week 6 |
| **3. Make It Yours** | Integrate dataset & custom logic | System solves ALPR problem | Weeks 12–13 | Weeks 7–8 |
| **4. Improve & Measure** | Test, tune & record metrics | Benchmark results recorded | Week 14 | Week 9 |
| **5. Package & Present** | Final demo video, docs & presentation | Final project submitted | Week 15 | Week 10 |

---

## Top Risks & Mitigations

1. **Poor Lighting & Glare at Night**
   * *Mitigation (Plan B):* Apply Contrast Limited Adaptive Histogram Equalization (CLAHE) preprocessing using OpenCV.
2. **Low OCR Accuracy on Degraded/Dirty Plates**
   * *Mitigation (Plan B):* Apply character bounding-box filters and rule-based regex validation matching standard state plate formats.

---

## Computing Resources
* **Environment:** Google Colab / Kaggle Free GPU (T4 Tensor Core)
* **Estimated Cost:** $0.00
