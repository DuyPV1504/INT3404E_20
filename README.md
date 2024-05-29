# Sino-Nom Character Localization - Group 5
This is a mid-term project for Image Processing Course INT3404E. This project aims to solve the problem of localizing Sino-nom characters in images using various object detections methods.  
To address this challenge, we propose two groups of deep learning models: two-stage detectors and one-stage detectors. The **R-CNN** family represents prominent examples of two-stage detectors, while **YOLO** and **SSD** are popular examples of one-stage detectors.  

## Our approach
As stated before, we explored 3 object detection models for the Sino-Nom Character Localization problem:   
1. **Faster RCNN:** Using Detectron2, an open-source library providing state-of-the-art detection and segmentation algorithms 
2. **YOLOv8:** Enhanced YOLO model with high accuracy using Ultralytics's YOLO.
3. **EAST:** Our reimplemntation of object detection algorithm described in the paper *"EAST: An Efficient and Accurate Scene Text Detector"*

With limited provided dataset and the rarity of public Sino-nom localization dataset, we applied various data augmentation methods to improve our dataset diversity.

## Result
Using Mean Average Precision (mAP) metrics and validation set in default dataset, the figure below illustrate accuracy of each of our proposed methods.
|  **Model**  | **mAP@[0.5,0.95]** |
|:-----------:|:------------------:|
| Faster RCNN |        0.34        |
|     EAST    |        0.34        |
|   **YOLO**  |      **0.93**      |

We can see that YOLOv8 out-performed our other preposed method with an mAP of approximately 0.93. Therefore, we chose YOLO as our main method.
On the mid-term evaluation day, we achieved 0.855 mAP@[0.5,0.95] on the new validation set provided by the profressor.
## Installation and Usage
For each of our methods installation and how to use them, we created a README file in each folder for each approach in **models** folder. In each file we describe how to use our model in more details.

## Repository's Structure
```
├── models #store 3 methods implementation
│   ├── EAST # Our first EAST method for object detections.
│   │   ├── Data # Store our dataset.
│   │   ├── README.md
│   │   ├── dataset.py
│   │   ├── detect.py
│   │   ├── loss.py
│   │   ├── metrics.py
│   │   ├── model.py
│   │   ├── requirements.txt
│   │   └── train.py
│   ├── FR-CNN # Our faster RCNN object detection methods.
│   │   ├── Faster R-CNN.ipynb # Jupyter notebook for training and evaluation
│   │   └── README.md
│   └── YOLO # Our YOLO implementation using Ultralytics library.
│       ├── README.md 
│       └── yolo.ipynb # Jupyter notebook for training and evaluation
└── sinoNom-data-preprocessing-augmentation # This folder contains our Jupyter notebook for data preprocessing and augmentation
    ├── sinoNom-data-augmentation.ipynb # Data Augmentation Jupyter notebook
    └── sinoNom-data-preprocessing.ipynb # Data Preprocessing Jupyter notebook
```

## Contributors
1. Phạm Thu Trang - 21020248
2. Phạm Vũ Duy - 21020179
3. Trần Phương Linh - 21020214
4. Đỗ Mạnh Dũng - 21020611
