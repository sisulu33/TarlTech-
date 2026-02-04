# Data Strategy

This document outlines how data is collected, processed, and used.

## Sources
- Farmer-submitted images
- Public agricultural datasets

## Storage
- Raw images
- Processed training data

## Ethics
- Consent
- Data privacy


## Selected Datasets

### PlantVillage (Maize Subset)
- Data type: Leaf images
- Classes: Healthy, Common Rust, Gray Leaf Spot, Northern Leaf Blight
- Approx size: ~3,000 images
- Source: Public research dataset
- Strengths: Clean labels, widely used
- Limitations: Controlled backgrounds

### Kaggle Maize Leaf Disease Dataset
- Data type: Leaf images
- Classes: Blight, Common Rust, Grey leaf spot, Healthy
- Approx size: 4000+
- Source: Kaggle community datasets
- Strengths: More diverse images
- Limitations: Label quality varies

### Initial Dataset Choice
For the first prototype, the plantVillage maize subset will be used due to clean labels and ease of experimentation.


# Dataset Overview

This project uses an image-based dataset of maize (corn) leaf diseases to train and evaluate a computer vision model for disease detection.

## Dataset Source
- Source: Kaggle – Corn or Maize Leaf Disease Dataset
- Image type: RGB leaf images
- Format: JPG/PNG
- Labels organized by folder (one folder per class)

## Classes and Image Counts

| Class            | Images |
|------------------|--------|
| Healthy          | 1162   |
| Gray Leaf Spot   | 574    |
| Common Rust      | 1306   |
| Blight           | 1146   |

**Note:** The dataset is moderately imbalanced, with fewer samples for Gray Leaf Spot.

## Data Integrity

- Corrupt images: ❌ None detected during initial loading
- All images were successfully opened using PIL
- No missing or unreadable files observed

## Image Properties

- Image sizes vary across the dataset
- Aspect ratios are not consistent
- Images will require resizing and normalization before training

**Planned preprocessing:**
- Resize all images to a fixed resolution (e.g. 224×224)
- Normalize pixel values to [0, 1]
- Apply data augmentation during training

## Dataset Split Strategy

The dataset is split into training and validation sets using an 80/20 ratio per class to ensure balanced evaluation.

| Class            | Train | Validation |
|------------------|-------|------------|
| Healthy          | 929   | 233        |
| Gray Leaf Spot   | 459   | 115        |
| Common Rust      | 1044  | 262        |
| Blight           | 916   | 230        |

This split allows:
- Reliable detection of overfitting
- Fair evaluation across all disease classes
- No data leakage between training and validation sets

## Future Considerations

- Class imbalance will be addressed using data augmentation and/or class weighting
- A separate test set may be introduced for final evaluation
