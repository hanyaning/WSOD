# Pseudo-labels Learning for Multi-source Weakly Supervised Salient Object Detection

## Prerequisite
* Python 3.7, PyTorch 1.1.0, and more in requirements.txt
* NVIDIA GPU with more than 1024MB of memory

## Data Preparation
* data/
      DUTS_TR/
             img_dir/
                    train/
                    test/
             ann_dir/
                    train/
                    test/

## Usage

#### Install python dependencies
```
pip install -r requirements.txt
```
#### Prepare initial pseudo labels
* To generate class activation maps using the classification network
  * python resnet50_cam.py
* To generate salient bounding box attributed maps with the detection network
  * python tools/BBAM/BBAM_FRCNN.py 
* To generate final pseudo-labels by by aggregating the two pseudo-labels mentioned above
  * python fusion.py

#### Train Segmenter with the generated pseudo labels
* python tools/train.py

## To do
* Code refactoring