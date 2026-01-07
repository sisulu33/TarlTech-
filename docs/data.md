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
