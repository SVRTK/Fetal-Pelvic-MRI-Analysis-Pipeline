# Dual-Network Pipeline for Fetal–Pelvic MRI Analysis

A deep learning-based pipeline for automated fetal and pelvic landmark segmentation, biometry extraction, and relative pose estimation in late-gestation 3D T2-weighted fetal MRI.

## 📌 Project Summary

This project was developed as part of my BEng Biomedical Engineering dissertation at King’s College London. The goal was to address the clinical need for an objective, automated method to assess fetal–pelvic compatibility in preparation for labor.

Using 3D MRI volumes and deep learning, this pipeline performs:
- Multi-label segmentation of fetal and maternal pelvic structures
- Automatic extraction of biometric and pelvimetric measurements
- Spatial pose analysis to estimate fetal head engagement
- Computation of composite clinical indices (FPI, HC/OC, Magnin Index)

---

## 🧠 Method Overview

The pipeline is divided into two main stages:

### 1. Model Training
- Two 3D U-Net models (pelvis & fetus) trained on T2-weighted MRI
- Manual annotations used for supervision (20 pelvis labels, 11 fetal)
- Data augmentation using MONAI for spatial, intensity, and class-specific transformations
- Progressive training rounds with DiceCE and Focal Loss

### 2. Testing & Analysis
- Applied to unseen MRI volumes
- Output segmentations used to compute clinical measurements:
  - BPD, OFD, HC, ISD, IC, MC, AP diameters
- Pose analysis performed via PCA-based engagement estimation
- Composite indices computed: FPI, HC/OC, Magnin Index

---

### 🙏 Acknowledgements
Supervised by Prof. Mary Rutherford, Dr. Alena Uus, and Dr. Simi Bansal.
MRI data from the MiBirth study at King’s College London.
Developed using the MONAI framework.
