# Breast Cancer Detection using Medical Imaging

A research-driven computer vision project for breast cancer detection and classification from mammography images. This work involves processing DICOM data, building high-quality annotations, and benchmarking object detection models (YOLOv8 and Faster R-CNN). The project is in progress, with ongoing work on tumor subregion classification and explainability using Grad-CAM.

---

## Project Objective

- Detect and localize breast cancer findings from mammogram scans.
- Handle large-scale DICOM data (~300+ GB, 20,000+ images).
- Benchmark object detection models on radiological findings.
- Explore explainable AI and detailed tumor subregion classification.

---

## Dataset Overview

- **Source**: [VinDr-Mammo Dataset](https://physionet.org/content/vindr-mammo/)
- **Structure**:
  
  ```
  raw_dicom_dir/
  ├── study_id_1/
  │   ├── image1.dcm
  │   ├── image2.dcm
  │   └── ...
  └── study_id_n/
      └── ...
  ```
  
- Each 'study_id' contains 4 mammography views.
- DICOM files are converted to PNG using 'pydicom' + OpenCV, with structure preserved.

---

## Annotation & Class Mapping

- Original annotations were multi-label.
- For initial benchmarking, each study was mapped to a **single dominant class**:
  - Mass
  - Focal Asymmetry
  - Asymmetry
  - Suspicious Calcification
  - Others (combined minor findings)
  - No Finding

> Work is ongoing to reintroduce more detailed subregion-level labels and extend this into finer-grained classification tasks, aligned with radiological annotation standards.

---

## Data Preparation Workflow

- Extracted and filtered annotations to remove overlap and ambiguity.
- Ensured **study-level split** to prevent data leakage.
- Downsampled 'No Finding' samples to ~10–20% of findings.
- Converted annotations to YOLO and COCO formats.
- Merged multiple datasets while avoiding duplicate 'image_ids'.

---

## Models Benchmarked

### YOLOv8

- Trained using a single-label object detection format.
- Basic hyperparameter tuning applied.
- Evaluation using mAP, precision, and recall.

### Faster R-CNN

- Dataset was converted to COCO format using custom scripts.
- Trained via Detectron2.
- Benchmarked on the same dataset as YOLOv8 for comparison.

---

## Benchmark Results (Preliminary)

> Results will be updated as model tuning and label refinement progress.

---

## Features In Progress

- **Tumor Subregion Detection**: Exploring annotations aligned with detailed regions within the tumor to improve diagnosis support.
- **Explainability**: Grad-CAM is under development as a post-processing step to visualize model predictions.
- **Model Monitoring**: Planned QA logic to validate outputs against medical rules.


## Roadmap

- Improve class definitions using original detailed annotations.
- Implement tumor part-based segmentation or classification.
- Integrate Grad-CAM for explainability.
- Deploy QA and edge-case validation tools.

---

## Acknowledgments

- VinDr Lab & PhysioNet for dataset access.
- Ultralytics and Facebook Research (Detectron2) for model frameworks.
- Arizona State University for infrastructure and project support.

