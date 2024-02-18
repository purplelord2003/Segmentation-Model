# Instance Segmentation Model (Urban Segmentor)

#### When I was doing the object detection model in the [`Object Detection Model repository`](https://github.com/purplelord2003/Object-Detection-Model), I actually came across the YOLOv8 architecture but did not end up using it and used a Faster R-CNN model instead. I decided that in this repository, we take things up a notch further to go beyond simple object detection to instance segmentation by applying masks to the instances and with the YOLOv8 architecture and get used to the Ultralytics interface.

#### This repository contains all the work I have done in the 2 Jupyter Notebooks in the `Jupyter Notebooks` folder. Do download the Jupyter Notebook's raw file to fix the formatting within the individual cells (the preview compresses the lines together) or open them in Google Colab using the links below. The Demo preparation folder contains the zip file that was then uploaded to Hugging Face spaces. You can access the built model demo application at https://huggingface.co/spaces/purplelord2003/Urban_Segmentor. 

# Summary
I attempted to train the [YOLOv8 model](https://docs.ultralytics.com/tasks/segment/) on the [cityscapes dataset](https://www.cityscapes-dataset.com/) for 50 epochs which was done in the [training notebook](https://github.com/purplelord2003/Segmentation-Model/blob/main/Jupyter%20Notebooks/Urban_Segmentor_(testing_and_deployment).ipynb). 

I then tested the model's speed in real-time by timing the frames per second of the output video from the model using OpenCV. I then created scripts and deployed the demo application on Hugging Face spaces. These were done in the [testing and deploying notebook](https://github.com/purplelord2003/Segmentation-Model/blob/main/Jupyter%20Notebooks/Urban_Segmentor_(testing_and_deployment).ipynb).
