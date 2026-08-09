# plant-disease-classification
plant disease classification using computer vision and deep learning
## Project Pipeline

The project follows a multi-stage Computer Vision and Deep Learning pipeline. First, the original plant images are preprocessed and enhanced using Gaussian filtering, HSV-based segmentation, CLAHE, and morphological operations. The main leaf region is then extracted and the background is replaced with white. Finally, CNN models are trained and evaluated using both original and enhanced images to measure the effect of the proposed preprocessing approach on plant disease classification.

```text
Original Images
      ↓
Gaussian Blur
      ↓
BGR → HSV
      ↓
CLAHE on V Channel
      ↓
HSV Green Segmentation
      ↓
Pale-Color Exclusion
      ↓
Morphological Refinement
      ↓
Contour / Central Object Selection
      ↓
Mask Dilation
      ↓
White Background Replacement
      ↓
Enhanced Dataset
      ↓
      ┌───────────────┐
      ↓               ↓
Original CNN    Enhanced CNN
      ↓               ↓
      └───────┬───────┘
              ↓
       Performance Comparison
              ↓
 Accuracy | Precision | Recall | F1
```

### Pipeline Summary

* **Preprocessing:** Noise reduction and contrast enhancement.
* **Segmentation:** HSV thresholding is used to identify green plant regions.
* **Mask Refinement:** Morphological operations and contour selection improve the segmentation quality.
* **Image Generation:** The selected leaf region is preserved while the background is replaced with white.
* **Classification:** CNN models are trained using both original and enhanced images.
* **Evaluation:** The two experiments are compared using standard classification metrics.
