# YOLO-CHKD

This repository contains the source code for the paper  


# Installation

Clone repo and create conda environment (recommended).
Then install requirements.txt in a Python>=3.8.0 environment, including PyTorch>=1.8.
The command is as follows.

```bash
git clone https://github.com/iMoonLab/Hyper-YOLO.git  # clone
cd Hyper-YOLO
conda create -n Hyper-YOLO python=3.8
conda activate Hyper-YOLO
pip install -r requirements.txt  # install
```
You can also use the environment.yaml file and the conda command to install the required environment.
```bash
conda env create -f environment.yaml
```

# Datasets
Data Preparation: Download the MS COCO dataset images (training, validation, and test sets) and corresponding labels, or prepare your custom dataset as shown below. Additionally, modify the dataset path in ultralytics/cfg/datasets/coco.yaml to reflect the location of your data.
```bash
coco
--images
  --train2017
  --val2017
--labels
  --train2017
  --val2017
```
# Training
Most of training configurations can change in the "Train settings" section of ultralytics/cfg/default.yaml. 
The key factors are model, data, img, epoches, batch, device and training hyperparameters.
For example, you can use "model: hyper-yolon.yaml" to train an object detection model.
```bash
python ultralytics/models/yolo/detect/train.py 
```

# Evaluation
Most of evaluation configurations can change in the "Val/Test settings" section of ultralytics/cfg/default.yaml. 
The key factors are model(weight), data, img, batch, conf, iou, half.
```bash
python ultralytics/models/yolo/detect/val.py
```
## Detection
Most of predict configurations can change in the "Predict settings" section of ultralytics/cfg/default.yaml.
The key factors are model(weight), source, img, conf, iou.
```bash
python ultralytics/models/yolo/detect/predict.py
```
![Detection](docs/vis_det.jpg)

# Acknowledgement
Our code is built based on the [YOLOv8](https://github.com/ultralytics/ultralytics).
Thanks for their great work!

# Citation



