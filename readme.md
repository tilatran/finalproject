# Ocean Garbage or Sea Creature Image Classification 

 This model classifies different types of trash as well as sea animals in order to help identify them in the water, where it may be harder to do so. This way, people can potentially avoid trash if they're trying to fish, avoid sea animals when trying to pick up trash, and be aware of what may be floating in the ocean. 

![classified cardboard](https://download1518.mediafire.com/llx0aqxswq8g/u5wf7ik4jx8ic0j/cardboard.png)

## The Algorithm

The algorithm utilizes imagenet in order to classify different images of trash or sea creatures and python scripts such as train.py, onnx_validate.py, and onnx_export.py to recreate and test the model on different devices. When training the model using the command " ", the nano learns how to differentiate the various trash from sea creatures by searching for similarities in each respective class. There are a total of 7 classes: cardboard, glass, paper, plastic, metal, trash and sea creature. The longer the training lasts, the more accurate the model will become. 


## Running this project

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
5. Export the model with onnx and use ctrl + D to exit the docker and set the variables
```
python3 onnx_export.py --model-dir=models/final_project
#Ctrl + D
cd jetson-inference/python/training/classification
NET=models/final_project
DATASET=data/final_project
```
6. Now, whatever photo you upload from the ocean can be classified using this string of code. I will use an example photo here: 
![alt text](https://www.greenbiz.com/sites/default/files/styles/og_image_1200x630/public/images/articles/featured/plasticbagoceandamseasstock.png?itok=lKtpNdhW)
```
cd jetson-inference/python/training/classification/data/final_project/test
wget https://download1321.mediafire.com/74f5rchjpulg/kv9n52gox1uymtw/testplastic.jpg
imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/testplastic.jpg plastic.jpg

```
After using the scp command to open the image in a terminal outside of the nano, we can see that it has been identified:



[View a video explanation here](video link)
