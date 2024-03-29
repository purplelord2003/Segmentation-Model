# Instance Segmentation Model (Urban Segmentor)
### Deployed app demo: https://huggingface.co/spaces/purplelord2003/Urban_Segmentor

## Introduction
When I was doing the object detection model in the [`Object Detection Model`](https://github.com/purplelord2003/Object-Detection-Model) repository, I actually came across the [YOLOv8](https://docs.ultralytics.com/) architecture but ended up using a pre-trained Faster R-CNN model in PyTorch (Torchvision) instead. I decided that in this repository, we take things up a notch further to go beyond simple object detection to instance segmentation by applying masks to the instances. I also decided to use the YOLOv8 architecture and get used to the Ultralytics interface, given that the YOLOv8 models (and their predecessors) have good inference accuracy with fast inference speeds, making it more feasible to be used in real-time detections/segmentations.

This repository contains all the work I have done in the 2 Jupyter Notebooks in the `Jupyter Notebooks` folder. Do download the Jupyter Notebook's raw file to fix the formatting within the individual cells (the preview compresses the lines together). The `Model Training and Testing` directory contains a `cityscapes.yaml` that I made for training as well as the results from the training. It also contains a folder `Testing` that contains the output testing videos from testing the model using my webcam and an imported video. The `Demo preparation` folder contains the zip file that was then uploaded to Hugging Face spaces as well as other essential files that were needed for the creation of the application.

### Open in Google Colab links:

[Notebook 1 (training)](https://colab.research.google.com/drive/1LjnUBLQ1y4mCEf9t-piHyEjE56BRC8I4)

[Notebook 2 (testing and deploying)](https://colab.research.google.com/drive/1HeJOGU8Qohar4UdGhGYpJfq-WUrGZKk1#scrollTo=393863ad-e30a-43d2-8ca8-cf9c889d4740)

## Summary
I trained the [YOLOv8 model](https://docs.ultralytics.com/tasks/segment/) on the [cityscapes dataset](https://www.cityscapes-dataset.com/) for 50 epochs which was done in the [training notebook](https://github.com/purplelord2003/Segmentation-Model/blob/main/Jupyter%20Notebooks/Urban_Segmentor_(testing_and_deployment).ipynb). This notebook can be run in Google Colab with no issues (though using the free GPU might still take many hours to finish the training). Personally, I used the A100 GPU from Google Colab Pro to accelerate my training time to just a few hours.

I then tested the model's speed in real-time by timing the frames per second of the output video from the model using OpenCV. I then created scripts and deployed the demo application on Hugging Face spaces. These were done in the [testing and deploying notebook](https://github.com/purplelord2003/Segmentation-Model/blob/main/Jupyter%20Notebooks/Urban_Segmentor_(testing_and_deployment).ipynb). This notebook may face issues when running in Google Colab especially the testing code cells as the `cv2.imshow()` will open an external display that Google Colab might not like, at least in my case. Hence, this notebook is preferred to be run in a local environment.

## Reflection
It was extremely user-friendly to use the Ultralytics interface in training the model as augmentation was automatically done on the images and optimal hyperparameters such as the learning rate and optimizer were also automatically used with learning rate decay, early stopping etc. The main issue I would say is that the interface requires a slightly rigid formatting of data (YOLO formatting) so I spent some time crafting a function to convert the data formatting in the cityscapes dataset into the required formatting for training. The creation of the Gradio demo app was slightly time-consuming to implement the various features inside. For the next project, I am considering to explore panoptic segmentation where we combine the best of both worlds (semantic segmentation + instance segmentation).
