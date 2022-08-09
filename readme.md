# Project Name

 This model classifies different types of trash as well as sea animals in order to help identify them in the water, where it may be harder to do so. This way, people can potentially avoid trash if they're trying to fish, avoid sea animals when trying to pick up trash, and be aware of what may be floating in the ocean. 

![add image descrition here](direct image link here)

## The Algorithm

Add an explanation of the algorithm and how it works. Make sure to include details about how the code works, what it depends on, and any other relevant info. Add images or other descriptions for your project here. 

The algorithm utilizes imagenet in order to classify different images of trash or sea creatures and python scripts such as train.py, onnx_validate.py, and onnx_export.py to recreate and test the model on different devices. When training the model using the command " ", the nano learns how to differentiate the various trash from sea creatures by searching for similarities in each respective class. There are a total of 7 classes: cardboard, glass, paper, plastic, metal, trash and sea creature. The longer the training lasts, the more accurate the model will become. 



## Running this project

1. Add steps for running this project.
2. Make sure to include any required libraries that need to be installed for your project to run.


2. Make sure you are in the directory "jetson-inference
The dataset for this project can be accessed with this link: . In order to download the dataset, use wget + , and unzip the folder using unzip

[View a video explanation here](video link)
