# Ocean Garbage or Sea Creature Image Classification 

 This model classifies different types of trash as well as sea animals in order to help identify them in the water, where it may be harder to do so. This way, people can potentially avoid trash if they're trying to fish, avoid sea animals when trying to pick up trash, and be aware of what may be floating in the ocean. 

![add image descrition here](direct image link here)

## The Algorithm

Add an explanation of the algorithm and how it works. Make sure to include details about how the code works, what it depends on, and any other relevant info. Add images or other descriptions for your project here. 

The algorithm utilizes imagenet in order to classify different images of trash or sea creatures and python scripts such as train.py, onnx_validate.py, and onnx_export.py to recreate and test the model on different devices. When training the model using the command " ", the nano learns how to differentiate the various trash from sea creatures by searching for similarities in each respective class. There are a total of 7 classes: cardboard, glass, paper, plastic, metal, trash and sea creature. The longer the training lasts, the more accurate the model will become. 



## Running this project

1. Add steps for running this project.
2. Make sure to include any required libraries that need to be installed for your project to run.

### You will need a Jetson Nano Development Kit, with the nano connected to the computer and internet as well as Resnet18 downloaded. The dataset can be accessed with this link: 

1. Make sure you are in the directory "jetson-inference/python/training/classification/data"
2. Access the dataset:
```
wget 
unzip latest.zip 
```
3. cd to jetson/inference and run 
```
./docker/run.sh
```
to get the docker container.

4. Train the nano. The longer it is left to run, the more accurate the results. About 15-20 minutes should suffice. 
```
cd jetson-inference/python/training/classification
python3 train.py --model-dir=models/final_project data/final_project

```
5. Export the model with onnx and use ctrl + D to exit the docker
```
python3 onnx_export.py --model-dir=models/final_project
#Ctrl + D
```
6. Now, whatever photo you upload from the ocean can be classified using this string of code. I will use an example photo here:
```
cd jetson-inference/python/training/classification/data/final_project/test
wget
unzip latest.zip
imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/testplastic.jpg plastic.jpg

```
After using the scp command to open the image on my own computer, we can see that it has been identified:



[View a video explanation here](video link)
