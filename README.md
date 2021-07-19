# YOLOF_Cars
YOLOF object detection implemented on Cars Dataset

#### Model : YOLOF (You Only Look One-Level Feature) , CVPR 2021, Detectron2
- is an object detector without FPN. 
- has two implementations based on cvpods and detectron2

Here, we have used the Detectron2 implementation
https://github.com/chensnathan/YOLOF

#### Dataset : Cars Dataset from Stanford-AI
- has 16185 images of 196 classes of Cars

https://ai.stanford.edu/~jkrause/cars/car_dataset.html

#### Codebase : MMDetection
- is an Object Detection toolbox and benchmark

https://github.com/open-mmlab/mmdetection

## Brief Description :  

At present a data pipeline has not been devised, since the focus is on experiments using YOLOF model on Cars Dataset.
Mainly, Google Colab has been used to perform the experiments. In the future, a continuous data pipeline and more generic methods will be implemented.

#### CarstoCoco 
- Loads dataset of 16185 images
- Splits the dataset into train, test, val in the given ratio (80/10/10 at present)
- Using the car_annos.mat, creates separate annotation files for train, test, val

#### YOLOF_Cars
- Loads the dataset
- Uses MMDetection model zoo to load model checkpoint and config
- Registers the CarsDataset as a custom dataset with the 196 classes similar to Coco dataset
- Adds/edits necessary configurations including the created annotation files 
- Trains the model with CarsDataset
- Performs inference using trained model.
