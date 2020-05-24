# Object Detection using [keras-Yolo v3](https://github.com/experiencor/keras-yolo3)

## Folder structure
```
.
├── Content
|   ├── Annotations
|   ├── train_images
|   ├── logs
|   └── ...
├── Output
|   ├── images
|   └── video
└── backend.h
└── kitchen.h
└── practice.ipynb

```

The **Content file** contains all the necessary folder, packages and codes required for the implementation of the model
- It contains the image folder required for training and evaluation 
- Weights required to initiate the training 
- The configuration file of the model which is used to tune various parameters in the model like
   - The number of epochs 
   - batch size
   - image min and max size
   - learning rate
   - Train image directory
   - ...
- The folder that saves checkpoints of the training
- Output folder that stores the results of the evalution

The **Output file** consists of a copy of the results obtained from the evaluation process. The results obtained is in the following format:
- image
- video

The **practice.ipynb** is the note book containing the complete code required to train an evalute the model.

The **.h files** are the pretrained weights used for training our model.

## Description of the model

The pretrained model use was obtained from [experiencor](https://github.com/experiencor). The model was trained on a kitchen [dataset](Project_Prog/Project_tasks/pract_yolo_3/Train_Images/) extracted from [indoor scene dataset](https://www.kaggle.com/itsahmad/indoor-scenes-cvpr-2019) from kaggle.The extracted dataset consisted of 300 images labelled with four labels
- oven
- kitchen sink
- refrigerator
- Range Hood

The data was labelled manually using [VoTT](https://github.com/microsoft/VoTT) software to label all the annotation of the images. The annotaion file generated by VoTT was in Pascal format (xml file) and was converted into Yolo format before intializing the training with the pretrained model. 

The data was trained with a pretrained [weights](Project_Prog/Project_tasks/pract_yolo_3/) to get better results and save training time. The weights were obtained from [Darknet](https://pjreddie.com/darknet/yolo/).

The data was trained for 50 epochs with batch size of 16 and object threshhold accuracy of 0.55. The tarining process took about 8 hours and the results is shown below
- [images](Project_Prog/Project_tasks/pract_yolo_3/output/)
- [video](Project_Prog/Project_tasks/pract_yolo_3/videos/)

sample of the output

 ![image 1](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/pract_yolo_3/output/p1010843.jpg)
 ![image 2](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/pract_yolo_3/output/rimg0408.jpg)
 ![image 3](https://raw.githubusercontent.com/osman-95/Project_Prog/master/Project_tasks/pract_yolo_3/output/p1000395.jpg)





