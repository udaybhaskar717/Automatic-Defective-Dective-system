# Automatic Defect Detection Dataset

This dataset consists of images of industrial components categorized into 15 different categories. Each category includes both defective and non-defective samples, with ground truth masks provided for defective samples in the test set. The dataset is designed for tasks such as defect detection, classification, and segmentation.

---

## Table of Contents
- [Dataset Overview](#dataset-overview)
- [Data Distribution](#data-distribution)
  - [Train Data](#train-data)
  - [Test Data](#test-data)
- [Image Specifications](#image-specifications)
- [Ground Truth Masks](#ground-truth-masks)
- [Category-Wise Summary](#category-wise-summary)
- [Key Insights](#key-insights)
- [Modeling Recommendations](#modeling-recommendations)
- [Acknowledgments](#acknowledgments)

---

## Dataset Overview
This dataset is curated for industrial defect detection and classification tasks. Each category includes:
- **Good (non-defective) samples** in the training set.
- **Defective samples** in the test set, with pixel-level ground truth masks.

The dataset aims to provide a diverse range of defect types, resolutions, and categories to challenge and evaluate machine learning models comprehensively.

---

## Data Distribution

### Train Data
- The training set contains only **good samples** (non-defective components).
- The number of training samples varies across categories, ranging from 60 (toothbrush) to 391 (hazelnut).

### Test Data
- The test set includes **both defective and non-defective samples**.
- Each category has specific defect types, providing a variety of challenges for model evaluation.

| **Category**      | **Train Good Samples** | **Test Defect Types**                             |
|--------------------|------------------------|--------------------------------------------------|
| Bottle            | 209                    | `broken_large`, `broken_small`, `contamination` |
| Cable             | 224                    | `bent_wire`, `cable_swap`, `cut_inner_insulation`, etc. |
| Capsule           | 219                    | `crack`, `faulty_imprint`, `poke`, `scratch`    |
| Carpet            | 280                    | `color`, `cut`, `metal_contamination`, etc.     |
| Hazelnut          | 391                    | `crack`, `cut`, `hole`, `print`                |
| Toothbrush        | 60                     | `defective`                                     |
| Wood              | 247                    | `color`, `combined`, `hole`, `liquid`, `scratch`|

---

## Image Specifications
- Image resolutions vary across categories but are consistent within each category.

| **Category**      | **Image Resolution** |
|--------------------|----------------------|
| Bottle            | 900x900              |
| Cable             | 1024x1024            |
| Capsule           | 1000x1000            |
| Carpet            | 1024x1024            |
| Hazelnut          | 1024x1024            |
| Toothbrush        | 1024x1024            |
| Wood              | 1024x1024            |
| Tile              | 840x840              |
| Metal Nut         | 700x700              |

---

## Ground Truth Masks
- Ground truth masks are provided for all defective samples in the test set.
- **Good samples** in both the train and test sets do not have ground truth masks, as they are defect-free.

---

## Category-Wise Summary
This dataset contains the following categories with corresponding defect types:

1. **Bottle**:
   - Train Samples: 209
   - Defect Types: `broken_large`, `broken_small`, `contamination`
   - Resolution: 900x900

2. **Cable**:
   - Train Samples: 224
   - Defect Types: `bent_wire`, `cable_swap`, `cut_inner_insulation`, etc.
   - Resolution: 1024x1024

3. **Capsule**:
   - Train Samples: 219
   - Defect Types: `crack`, `faulty_imprint`, `poke`, `scratch`
   - Resolution: 1000x1000

4. **Carpet**:
   - Train Samples: 280
   - Defect Types: `color`, `cut`, `metal_contamination`, etc.
   - Resolution: 1024x1024

5. **Hazelnut**:
   - Train Samples: 391
   - Defect Types: `crack`, `cut`, `hole`, `print`
   - Resolution: 1024x1024

6. **Toothbrush**:
   - Train Samples: 60
   - Defect Types: `defective`
   - Resolution: 1024x1024

7. **Wood**:
   - Train Samples: 247
   - Defect Types: `color`, `combined`, `hole`, `liquid`, `scratch`
   - Resolution: 1024x1024

---

## Key Insights
- **Consistency**: Image resolutions are consistent within each category, simplifying preprocessing.
- **Defect Diversity**: Multiple defect types are present in each category, ensuring robust model evaluation.
- **Data Quality**: No corrupted images were found in the dataset, ensuring high-quality data.
- **Smallest Dataset**: Toothbrush has the smallest training set, which may require augmentation to prevent underfitting.

---

## Modeling Recommendations
1. **Preprocessing**:
   - Resize images to a consistent resolution if necessary.
   - Normalize pixel values for model input.
2. **Augmentation**:
   - Apply augmentations like rotation, flipping, and scaling, especially for categories with fewer samples (e.g., toothbrush).
3. **Segmentation Models**:
   - Use models like U-Net or Mask R-CNN for defect detection and segmentation using ground truth masks.
4. **Classification Models**:
   - Train models to classify defective vs. non-defective samples.
5. **Imbalanced Data Handling**:
   - Apply oversampling or weighted loss functions for categories with fewer defects.

---

## Acknowledgments
This dataset is intended for research and development purposes to advance defect detection techniques in industrial applications.
