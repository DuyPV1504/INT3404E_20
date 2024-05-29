## Description
This is our group implementation of transfer learning using YOLOv8 pretrained model.

## Prerequisites
You can easily use our trained model with Ultralytics YOLOv8, which can be installed with

```
pip install ultralytics
```

## Model
You can download our final model from Google drive: [drive](https://drive.google.com/file/d/1AgbTRbOLfV7szyyk_PYRueYkU7On5oIi/view?usp=sharing)
## Structure
This folder contains a jupiter notebook which we used for our model training on Google Colab.
```
.
├── README.md
└── yolo.ipynb
```

## Detect
Using Ultralytics yolo commandline, you can easily use our group model to detect Sino-nom word objects in images.   
Example:
```
yolo task=detect mode=predict model='path to our model' source='path to images folder' save=False verbose=True save_txt=True save_conf=True
```
