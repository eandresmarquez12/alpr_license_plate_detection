# Automatic License Plate Recognition (ALPR) System
ITAI 1378 Midterm Blueprint - Automated License Plate Recognition System

## Team Members
* **Edwin Marquez** ([@eandresmarquez12](https://github.com/eandresmarquez12))
* **Chris Roy** ([@ChrisRoyHCC](https://github.com/ChrisRoyHCC))
* **Unnati Shakya** ([@unnatishakya](https://github.com/unnatishakya))
* **Njeh Ababio** ([@NjehAbabio](https://github.com/NjehAbabio))

---

## Project Tier
**Tier 1 – Core**

This project focuses on building a robust end-to-end computer vision pipeline that detects license plates in vehicle images using a pretrained YOLO model that is fine-tuned on a pre-annotated, single class (license_plate) dataset. 

---

## Problem Statement
Manual vehicle logging in private parking facilities and toll booths causes congestion, increases operational labor costs, and introduces human error during peak traffic hours. Parking and traffic monitoring systems lose thousands of dollars every month in delayed entry and unbilled access. Automated License Plate Recognition (ALPR) provides a reliable, scalable solution to process vehicle entries seamlessly in real time.

---

## Solution Overview
An automated computer vision system that captures vehicle images, detects and crops license plate regions using Yolo object detection model, then outputs an annotated image and a cropped plate region. YOLO finds plates in a single pass, so it works well on a small dataset. 

**Pipeline Flow:**  
`Vehicle Image` ➔ `YOLO Plate Detector` ➔ `Annotated Output (bounding box)` + `Cropped Plate Region`

---

## Technical Approach
* **Computer Vision Task:** Object Detection 
* **Detection Model:** Ultralytics YOLO (PyTorch), fine-tuned from pretrained weights
* **Frameworks:** PyTorch, Ultralytics YOLO, OpenCV

---

## Data Plan
* Source: License Plate Dataset by Ronak Gohil (Kaggle)
* Dataset Size: 1,695 annotated vehicle images
* Preprocessing: Images reviewed for coordinate accuracy and normalized to 640 x 640 resolution
* Splits: 80% Training, 10% Validation, 10% Testing
* Labels: Bounding boxes in YOLO format for a single class, `license_plate`


---

## Success Metrics
* Primary Metric: Detection mAP@50 ≥ 0.70
* Secondary Metrics: Precision ≥ 0.80; Inference latency ≤ 100 ms per image

---


## Milestone Schedule

| Step | Goal | Schedule |
|---|---|---|
| **01** | Submit proposal, outline project architecture, and create GitHub repository | Week 10 |
| **02** | Run a pretrained YOLO model end-to-end on a few license-plate images | Week 11 |
| **03** | Prepare and validate the Kaggle data, fine-tune YOLO, show training curves, build the crop/annotate pipeline | Week 12 & 13 |
| **04** | Run the held-out test set and record mAP@50, precision, and latency; fix issues such as glare | Week 14 |
| **05** | Demo video, final README, final slides | Week 15 |
---

## Top Risks & Mitigations

* Dataset Quality (inconsistent, missing, or hard-to-detect plates)
Mitigation (Plan B): Clean annotations, apply data augmentation, or switch to an alternate public dataset.

* Model Performance (issues with lighting, angles, distances, occlusions)
Mitigation (Plan B): Further fine-tuning, adjust training parameters, or limit scope to clear plate images.


---

## Computing Resources
* Environment: Google Colab free GPU / Kaggle free GPU
* Tools: Ultralytics YOLO + PyTorch (open source)
* Estimated Cost: $0.00
