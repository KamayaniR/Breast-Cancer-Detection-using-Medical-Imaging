# Deep Learning-based Detection of Breast Cancer Findings in Mammography

This repository contains ongoing research focused on localizing breast cancer-related abnormalities in mammograms using deep learning-based object detection techniques. The primary objective is to develop an explainable, high-performance detection pipeline to assist radiologists with early diagnosis and screening support.

## Project Overview
Breast cancer is one of the leading causes of cancer-related deaths among women globally. This project explores automated detection of abnormalities in mammograms through computer vision, utilizing multiple deep learning models.

## Dataset Details
Dataset: VinDr-Mammo Dataset
- Contains mammography studies with radiologist-annotated findings.
- Includes common findings such as:
  Mass,
  Focal Asymmetry,
  Asymmetry,
  Suspicious Calcification,
  Others (rare or combined findings),
  No Finding (downsampled for class balancing)
## Preprocessing Steps:
- DICOM to PNG conversion.
- Study-wise train/validation/test split (90/5/5) to prevent data leakage.
- Annotation conversion to YOLO format.
- Image augmentation & resizing (during training).

## Models & Techniques

  | Model                   | Type        | Status            |
| ----------------------- | ----------- | ----------------- |
| YOLOv8                  | One-Stage   | Completed         |
| Faster R-CNN            | Two-Stage   | In Progress       |
| Deformable DETR         | Transformer | Exploration Phase |

## Core Techniques:
- Object Detection (Bounding Box Localization)
- Stratified Dataset Splitting (by StudyID)
- Data Augmentation & Resizing
- Class Re-weighting & Focal Loss (planned)
  
### Explainable AI:
- Grad-CAM for object detection
- Bounding Box Visualizations
- Upcoming SHAP/LIME explorations


