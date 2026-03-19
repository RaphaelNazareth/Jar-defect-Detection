# Jar Lid Defect Detection — YOLOv8
<img width="1312" height="812" alt="image" src="https://github.com/user-attachments/assets/7fccbff5-6bb2-4c84-b9d5-ac6a5daed884" />

## Overview

Product defects in manufacturing can lead to financial losses and safety risks. Manual inspection is often inconsistent and inefficient, especially in high-volume production.

This project develops a computer vision–based defect detection system using **YOLOv8** to automatically detect and classify jar lids as:

- **intact**
- **damaged**

---

## Dataset

- Source: https://www.kaggle.com/datasets/rrighart/jarlids  
- Total images: **168**  
- Total annotations: **1,859**  

### Classes
- damaged  
- intact  

### Data Split
- Train: 139  
- Validation: 24  
- Test: 5  

---

## Methodology

### 1. Data Preprocessing
- Converted annotation from CSV (VIA format) → YOLO format  
- Extracted bounding boxes (xmin, ymin, xmax, ymax)  
- Normalized to YOLO format (x_center, y_center, width, height)  

### 2. Dataset Structure
```
images/
  train/
  val/
  test/
labels/
  train/
  val/
  test/
```

### 3. Model
- YOLOv8n (pretrained)
- Fine-tuned on custom dataset
- Number of classes: 2

### 4. Training Configuration
- Epochs: 50  
- Image size: 640  
- Batch size: 16  
- Early stopping: 15  

---

## Results

### Validation Metrics

| Metric        | Value   |
|--------------|--------|
| mAP@0.5      | 0.9799 |
| mAP@0.5:0.95 | 0.9240 |
| Precision    | 0.9455 |
| Recall       | 0.9611 |

---

## Model Comparison (YOLOv7 vs YOLOv8)

| Metric        | YOLOv7 | YOLOv8 |
|--------------|--------|--------|
| mAP@0.5      | 0.675  | 0.9799 |
| mAP@0.5:0.95 | 0.378  | 0.9240 |
| Precision    | 0.524  | 0.9455 |
| Recall       | 0.866  | 0.9611 |

---

## Visualizations

### Class Distribution
<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/08eb2565-f415-41cd-80ce-dcb2321fdb73" />

### Bounding Box Samples
<img width="616" height="490" alt="image" src="https://github.com/user-attachments/assets/224bbf70-2fb6-43d1-850f-73ec97211ae0" />

### Training Curves
<img width="1589" height="789" alt="image" src="https://github.com/user-attachments/assets/53a5fc02-6604-4678-a26d-bd6f65171a6a" />

### Test Predictions
<img width="1489" height="923" alt="image" src="https://github.com/user-attachments/assets/5d62c457-e757-4b11-b3a7-4f0889c7d13c" />


---

## Conclusion

The YOLOv8 model achieves strong performance across all evaluation metrics, demonstrating its effectiveness for automated defect detection using a relatively small dataset.

---

## Limitations

- Small dataset size  
- Limited variation in environment and lighting  
- Binary classification only  

---

## Future Work

- Expand dataset with more diverse samples  
- Add fine-grained defect categories  
- Apply advanced data augmentation  
- Benchmark with additional models  

---

## References

Ahmed, I., Siddiqi, M. U. R., & Ahmad, M. (2024).  
*AI-Enhanced Visual Inspection Systems for Robust Detection of Product Packaging Defects in Manufacturing Environments.*  
IEEE UEMCON 2024.

##Author
## Author

## Author
**Raphael Nazareth** Computer Engineer | AI / Data Science

- [GitHub](https://github.com/RaphaelNazareth)
- [LinkedIn](https://www.linkedin.com/in/raphael-nazareth)
- [Email](mailto:Raph00707@gmail.com)
