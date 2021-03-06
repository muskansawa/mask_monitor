# mask_monitor

## Project Overview

### Objectives:
The aim of this project is to detect whether a person is wearing a face mask or not by capturing input from the camera and testing it on a Face Mask detection Model.  If our model detects a face without a mask, it will capture the image and store it in a database for record. After doing all this, if time permits, then the next improvement will be identifying the defaulters by using the data stored previously. 

### Flow of the project:
![image](https://user-images.githubusercontent.com/44108897/124584433-e172cd00-de71-11eb-9c1c-d94f07a3e1f8.png)



## Resources and Dependencies

+  python installed
+  anaconda ide or a virtual env with python and other dependencies.
+  mySQL
+  OpenCV , MySQL Connector, NumPy , keras and tensorflow  python libraries.
+  Haarcascade frontal_face.xml file
+  CPU or a GPU(fast compute preferred).
+  large dataset for training 




## LIVE DEMO

[Real time mask detection](https://github.com/muskansawa/mask_monitor/blob/main/result/sample.mp4)

https://user-images.githubusercontent.com/44108897/124388523-fd0a9600-dd00-11eb-8e3d-14418dac9351.mp4



## data preprocessing

+ here we will load the data from our dataset to organise and convert them into a format which can be given as an input to our CNN
+ tf.keras.applications.vgg16.preprocess_input is used to preprocess our data to send into our VGG16 model
![image](https://user-images.githubusercontent.com/44108897/124586693-5e06ab00-de74-11eb-9d1c-4d966b5edc77.png)

## training 
 - i used 12K  dataset from kaggle and trained my model on 10000 images
 - val_accuracy: 0.9975
 
## testing
 Check for the accuracy using a confusion matrix and plotting it using matplotlib’s pilot module.
 ![image](https://user-images.githubusercontent.com/44108897/124589513-b4291d80-de77-11eb-841a-981f0b15b1fe.png)


## Updating the database with labelled images from our local directory:

- we can move on to loading the image into our model and classifying a face as with or without mask and store the labels 
- the image of a person without a mask is captured and saved in our local directory. After regular intervals we send that data from the local directory to our MySQL database by   running our python script sql.py. 
- The name of our table is pic
- It stores 3 parameters (the id of defaulter, name if known, the image captured).

![image](https://user-images.githubusercontent.com/44108897/124589993-429d9f00-de78-11eb-9212-d2b8c41e9a42.png)


![image15](https://user-images.githubusercontent.com/44108897/124587531-5693d180-de75-11eb-9650-ee4e8bf34ec2.png)

