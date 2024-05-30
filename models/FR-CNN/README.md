## Description
This folder contains the implementation of Faster R-CNN for object detection using Detectron2.

## Prerequisites
You can set up the environment and run the code using the following commands:
```bash
pip install torch torchvision opencv-python
pip install 'git+https://github.com/facebookresearch/detectron2.git'
```

## Structure
This folder contains our Jupyter notebook that was used to train our model.
```
.
├── README.md
├── train.ipynb
└── utils
    ├── dataset.py
    └── config.py
```

## Detect

cfg.MODEL.WEIGHTS = "path/to/your/model_final.pth"
cfg.MODEL.ROI_HEADS.SCORE_THRESH_TEST = 0.5
cfg.MODEL.DEVICE = "cuda"

predictor = DefaultPredictor(cfg)
evaluator = COCOEvaluator("your_dataset_val", output_dir="./output")
val_loader = build_detection_test_loader(cfg, "your_dataset_val")


