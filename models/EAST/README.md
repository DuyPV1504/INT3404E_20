## Description
This is a PyTorch Re-Implementation of [EAST: An Efficient and Accurate Scene Text Detector](http://openaccess.thecvf.com/content_cvpr_2017/papers/Zhou_EAST_An_Efficient_CVPR_2017_paper.pdf).

Code to build and train model was mostly adapted from the repository: [https://github.com/SakuraRiven/EAST](https://github.com/SakuraRiven/EAST).

Code to evaluate the mAP@.5:.95 metric was mostly adapted from the code provided by the TA. 
## Prerequisites
Only tested on
* Anaconda3
* Python 3.7.1
* PyTorch 1.0.1
* Shapely 1.6.4 
* opencv-python 4.0.0.21
* lanms 1.0.2

When running the script, if some module is not installed you will see a notification and installation instructions. __if you failed to install lanms, please update gcc and binutils__. The update under conda environment is:

    conda install -c omgarcia gcc-6
    conda install -c conda-forge binutils

The original lanms code has a bug in ```normalize_poly``` that the ref vertices are not fixed when looping the p's ordering to calculate the minimum distance. We fixed this bug in [LANMS](https://github.com/SakuraRiven/LANMS) so that anyone could compile the correct lanms. However, this repo still uses the original lanms.

## Installation
### 1. Clone the repo

```
git clone https://github.com/DuyPV1504/INT3404E_20_Group5
cd INT3404E_20_Group5/models/EAST
```

### 2. Data & Pre-Trained Model
* Download our trained EAST model: [EAST](https://drive.google.com/file/d/1Ew2hB2mT4VdWr6Iywa4dYLE02H4wNhlz/view?usp=drive_link). Make a new folder ```pths``` and put the download pths into ```pths```
  
```
mkdir pths
mv model_epoch_10.pth pths/
```
## Train
* Modify the parameters in ```train.py``` and run:
```
CUDA_VISIBLE_DEVICES=0,1 python train.py
```
## Detect
* Make a new folder ```Submit``` where we will put the result which model detect on validset into
```
!mkdir Data/Valid/Submit
```
* Modify the parameters in ```detect.py``` and run:
```
CUDA_VISIBLE_DEVICES=0 python detect.py
```
## Evaluate
* Set up:
``
    pip install -r requirements.txt
``
* Modify the parameters in ```eval.py``` and run to obtain mAP@.5:.95 score of our model on validset:
```
!python metrics.py --gt Data/Valid/Labels --pred Data/Valid/Submit --img Data/Valid/Images
```
