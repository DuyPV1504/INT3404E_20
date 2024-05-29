# Sino-Nom Character Localization - Group 5
This is a mid-term project for Image Processing Course INT3404E. This project aims to solve the problem of localizing Sino-nom characters in images using various object detections methods.  
To address this challenge, we propose two groups of deep learning models: two-stage detectors and one-stage detectors. The **R-CNN** family represents prominent examples of two-stage detectors, while **YOLO** and **SSD** are popular examples of one-stage detectors.  

## Our approach
As stated before, we explored 3 object detection models for the Sino-Nom Character Localization problem:   
1. **Faster RCNN:** Using Detectron2, an open-source library providing state-of-the-art detection and segmentation algorithms 
2. **YOLOv8:** Enhanced YOLO model with high accuracy using Ultralytics's YOLO.
3. **EAST:** Our reimplemntation of object detection algorithm described in the paper *"EAST: An Efficient and Accurate Scene Text Detector"*

With limited provided dataset and the rarity of public Sino-nom localization dataset, we applied various data augmentation methods to improve our dataset diversity.

## Installation and Usage
For each of our methods installation and how to use them, we created a README file in each folder for each approach in **models** folder. In each file we describe how to use our model in more details.

## Repository's Structure
