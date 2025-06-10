# Diabetic Retinopathy Detection Using Transfer Learning (ResNet50)

## Project Overview
This project aims to classify fundus images into five categories of Diabetic Retinopathy (DR) severity:
- No_DR
- Mild
- Moderate
- Severe
- Proliferative_DR

Using transfer learning with the ResNet50 architecture, this model helps automate early detection of diabetic retinopathy, a leading cause of blindness.

## Dataset
- The dataset is split into training, validation, and test sets.
- Data augmentation techniques (rotation, zoom, shear, brightness adjustment, horizontal flip) were applied to improve model generalization.
- Class imbalance handled via class weighting.

## Model Architecture & Training
- Base model: Pre-trained ResNet50 (ImageNet weights), with top layers removed.
- Custom classification head added with Dense and Dropout layers.
- Training done in two phases:
  - Phase 1: Freeze base layers and train only the custom head.
  - Phase 2: Unfreeze last 50 layers for fine-tuning with a lower learning rate.
- Mixed precision training used to optimize performance and memory usage.

## Performance
- Achieved **67% test accuracy** on 5-class classification.
- Model evaluated using confusion matrix and classification report.
