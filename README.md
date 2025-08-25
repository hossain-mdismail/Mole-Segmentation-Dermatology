# Mole Segmentation for Dermatology

## Project Overview
This project presents an image preprocessing and segmentation pipeline designed to support dermatologists in the classification of skin moles.  
Accurate segmentation of mole regions is a critical step in computer-aided dermatology, as it provides a reliable foundation for subsequent classification tasks (e.g., distinguishing between benign and malignant lesions).  

The notebook included in this repository demonstrates the application of unsupervised machine learning methods combined with image processing techniques to extract clean mole contours from skin images.

---

## Objectives
- Isolate mole regions from skin images with minimal noise.  
- Remove background artifacts such as shadows and reflections.  
- Generate smooth and accurate mole borders suitable for medical inspection.  
- Provide preprocessing suitable for future classification models.  

---

## Methodology
The proposed pipeline is composed of the following steps:

1. **Color Quantization using K-Means Clustering**  
   The image is reduced to three color clusters, separating skin, mole, and background. This reduces variability and simplifies segmentation.

2. **Darkest Cluster Extraction**  
   The darkest cluster is assumed to correspond to the mole region and is extracted for further analysis.

3. **Spatial Clustering using DBSCAN**  
   The coordinates of the darkest cluster are grouped using DBSCAN in order to remove isolated pixels and shadows. DBSCAN ensures that only spatially coherent regions are retained.

4. **Mole Region Identification**  
   Among the detected clusters, the mole is selected based on two criteria:  
   - A relatively large number of points (area).  
   - A low moment of inertia, indicating compactness.  

5. **Contour Extraction and Smoothing**  
   The selected region is processed to extract and refine its contour. Additional filtering is applied to obtain a smooth and medically interpretable mole border.  



## Example Results



