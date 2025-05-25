# Breast Cancer Detection with Deep Learning
YOLO-based medical imaging pipeline for early cancer detection, trained on high-resolution annotated images.
# Breast Cancer Detection using YOLOv8

## Overview
This project aims to detect and classify breast cancer-related features from mammography images using object detection models (YOLOv8). The project follows FDA guidance on AI-assisted diagnosis and incorporates BIRADS-based stratification and mass-level annotations.

## Dataset Summary: VinDr-Mammo on Kaggle
Content:
  - Over 5,000 mammography exams (2 views per breast: L-CC, R-CC, L-MLO, R-MLO)
  - BIRADS assessment categories
  - Annotations in CSV format (bounding boxes, lesion types)
  - View position + breast density info
  - Labels: mass, calcification, asymmetry, architectural distortion

