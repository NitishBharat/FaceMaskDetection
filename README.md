# FaceMaskDetection
Real-Time Implementation of AI-Based Face Mask Detection and Social Distancing Measuring System for COVID-19 Prevention
The basic aim of the project is to detect the presence of a face mask on human faces as on images.To monitor that people are following this basic safety principle, A face mask detector system can be implemented to check this. Face mask detection means to identify whether a person is wearing a mask or not. The ﬁrst step to recognize the presence of a mask on the face is to detect the face, which makes the strategy divided into two parts: to detect faces and to detect masks on those faces. Face detection is one of the applications of object detection and can be used in many areas like security, biometrics, law enforcement and more.In making of this project we have two phases .

Train model using Convolution or any pretrained model which detect face masks in images .
Then, Detect faces in video or images and get prediction from our trained model .
In this Project I used Transfer learning to train model on dataset provided in drive link attached in file 

Dataset
In the Dataset we have two types of images one who wore mask and other which do not have mask.

Training Dataset consist of 1375 images in which 685 images have label with mask and 690 images are of without mask faces and Validation Dataset consist of 50 .


Import :
First I import Required modules like tensorflow , keras ,optimizer , layers and pretrained model
Loading Data And Augment Image :
Now I load all images for training and preprocess

we also Augment our images through which we can get more data and variety in data. we add augmentation technique like zoom , horizontal and vertical flip , rotation .

After this step we have training and validation batches of shapes which mobilenetv2 require as input .

Adding Some More layers To Model :
Adding Some Layer at the end of the model to achieve good accuracy or save model from overfitting .

At last add one fully connected layer which contains neurons equal to number of labels we have (In this case we have 2 labels mask or no mask) . And After Define Model Input and output layer .

Now Our Model Structure is ready .


Compile and Train :
Now it’s time to train the model but before training we have to define loss function and optimizer i.e., compiling a model .

After Hypertuning of parameters I found good results with Learning Rate 0.00001 . So , I used Adam Optimizer with learning Rate 0.00001 and loss function binary_crossentropy . then after I trained the model with 15 epochs and validate it on validation data (which contains 300 images) .


Testing Phase :
Now we have to test model on test data through which we got good idea weather model will work good on real time data or not . so , we have 74 images of 2 classes as test dataset after evaluating it on test dataset I got good results .

Loss : 0.058


Confusion Matrix :
A confusion matrix is a table that is often used to describe the performance of a classification model on a set of test data for which the true values are known.

After Plotting Confusion Matrix what I see My Trained Model only predicts 1 image wrong else all images are correctly predicted . so model will work Good in Realtime .

