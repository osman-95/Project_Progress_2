# Object detection-based Scene Classification
**NOTE- The current progress in the code implemented is illustrated in the [**Final_Model**](https://github.com/osman-95/Project_Progress_2/tree/master/Final_Model) file**

**NOTE- The Final_Model folder contains all the codes, datasets and models implemented for the main objective of the project**

**NOTE- The Project_tasks folder contains all the concepts, codes and models learned and tested in the initial learning stage of the project **

The main aim of the project is to design a real-time scene classification model to classify an image based on the objects detected in the image. The model is trained on all the possible combinations of objects that can appear in a frame/image to constitute a specific class (for example, if the objects detected in a frame/image are an oven, refrigerator, microwave and a sink, the model can determine the class of the image as kitchen).
The project can be divided into two parts,

- Detection of objects in an image
- Classification of the image based on the detected object

The object detection model is trained using a dataset of images of various indoor scenes (classes), with each having annotations/labels of various objects in the image. The dataset is trained with a pre-trained object detection model, Mobilenet v2. It was chosen for its high speed and fast training, which makes it suitable for real-time object detection.  

To classify an image based on the objects detected in a frame/image, the annotations generated for each frame by the object detector are trained on a classification model. The annotations generated by the images will be used to generate a tabular dataset containing all the information about the number of occurrences of each detected object and the class that it belongs to. The classification models that will be used are Linear SVC, K-Neighbors Classifier and Naïve Bayes. Based on the accuracy and speed of the models, one model will be chosen for classification.

While testing the model, the annotations or labels detected by the object detection model are fed to the classification model to determine the class of the image.

Before Elaborating the above sections, a quick overview on the file hierarchy of the main files are shown below
         
```   
 
├── Project_tasks
│   ├── Mobilenet (Mobilenetv2 using Tensorflow API)
|   ├── Yolo_3 (Yolo 3 by AntonMu on Github)
|   ├── pract_yolo_3 (yolo 3 mmodel by experiencor Github)
│   ├──classification (using pretrained Mobilenet classification model)
|   └──scratch_class (CNN from scratches) 
|        
└── Final_Model (Note: In progress last updated on 10th of july)
     └── Code
     └── Dataset

 ```       
**NOTE:**
- **The Project task displays all the the object detection models and Image classification models learnt and  tested during the previous period to understand the working procedure and the time consumption in training process of each model.** 
- **The Image classification models were just implemented for the sake of learning and will not be used in the final model implementation.**
- **The file named as "Final_Model" will be updated soon with the final model progress**

## Description of the dataset
The dataset was created by MIT, and was obtained from [Kaggle](https://www.kaggle.com/itsahmad/indoor-scenes-cvpr-2019?). It consists of 67 categories/classes and a total of 15,620 images of a variety of indoor scenes such as classrooms, restaurants, bars, bakeries, bathrooms, libraries, bedrooms, airports, etc. The number of images in each category varies, but there are at least 100 images per category and all the images are in .jpg format. 

![Dataset](https://raw.githubusercontent.com/osman-95/Project_Prog/master/ReadMe_img/Capture1.PNG)

Only 6 classes were chosen to be worked on, with each containing 100 images. The decision to choose only 6 classes was made due to time constraints and hardware limitations. The 6 classes chosen were bedroom, bathroom, dining room, kitchen, bowling center, and office.

 ![Selected categories](https://github.com/osman-95/Project_Progress_2/blob/master/ReadMe_img/Capture12121.PNG)

I labelled the dataset manually using [VoTT software](https://github.com/microsoft/VoTT), with each class having at least 4 different types of annotations/labels. 

 ![](https://github.com/osman-95/Project_Progress_2/blob/master/ReadMe_img/Capture21211.PNG)

## Task Completed
Following is a short breakdown of the tasks I have completed thus far.
- I conducted background research to familiarize myself with the concept of object detection and with classification models. This was followed by some reading aimed at understanding the procedure of executing and training of a dataset on a pre-trained model.

- To implement was I had learnt, I worked on a sample dataset consisting of 300 images of kitchen scenes with 4 annotation types to understand how to implement object detection on a pretrained model. The sample dataset for object detection consisted of 300 images of kitchen with four labels shown below

         -> oven

         -> refrigerator

         -> range hood

         -> kitchen sink

- Three pre-trained model were examined, namely [Mobilenet v2 (TensorFlow API)](), [Yolo v3 (experiencor)]() and [Yolo v3 (AntonMu)]() and sample of the output of each model is shown below.

  - **Mobilenet v2**
  
  
    ![](https://github.com/osman-95/Project_Progress_2/blob/master/Project_tasks/Mobilenet/Output/M_img.png)
    ![](https://github.com/osman-95/Project_Progress_2/blob/master/Project_tasks/Mobilenet/Output/M_img2.png)
  - **Yolo v3 (Model_1)**
  
    ![image 1](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/pract_yolo_3/output/p1010843.jpg)
    ![image 2](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/pract_yolo_3/output/rimg0408.jpg)
    ![image 3](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/pract_yolo_3/output/p1000395.jpg)

    
  - **Yolo v3 (Model_2)**
  
    ![](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/Yolo_3/TrainYourOwnYOLO_AM/Data/Source_Images/Test_Image_Detection_Results/VA-02-04-7657-02_l_catface.jpg)
    ![](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/Yolo_3/TrainYourOwnYOLO_AM/Data/Source_Images/Test_Image_Detection_Results/N364080_catface.jpg)
    ![](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/Yolo_3/TrainYourOwnYOLO_AM/Data/Source_Images/Test_Image_Detection_Results/N364071_catface.jpg)
    

- Two image classification models, that is, a pre-trained Mobilenet classification model and a convolutional Neural Network that I built myself, were executed on a different dataset containing 6 classes with 100 images each, to understand the working of image classification models.The sample data used for classification consisted of 6 indoor categories listed below

         -> bedroom

         -> bar

         -> bakery

         -> bathroom

         -> auditorium

         -> artstudio


**NOTE:** Image classification model were mainly implemented for understanding purpose the concept of image classification only. The results might be used for comparison later when the final model is built for evaluation and  justification. 

  - **Classification_1 (Mobilenet v2)**
  
    ![](https://raw.githubusercontent.com/osman-95/Project_Prog/master/ReadMe_img/Capture3.PNG)
    
  - **Classification_2 (CNN from scratches)**
  
    ![](https://raw.githubusercontent.com/osman-95/Project_Prog/master/ReadMe_img/Capture4.PNG)

## Upcoming Tasks to be completed
I am currently working on the following,
- Labeling my final dataset.
- Writing a code to generate a dataset by extracting the annotations information from the annotation .csv file to train it to a classification model. 
- After building an object detection model, writing a code to extract the annotations/labels from the output of the object detector. This extracted information (labels/annotations) will be fed to the classification model for determining the class of the image.



