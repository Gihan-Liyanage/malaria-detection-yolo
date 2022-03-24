# Malaria Parasite Detection using YOLO (V3 & V4)
@Authors: Gihan Liyanage, Chamithri Weerakoon

## General Information
YOLO (YOU ONLY LOOK ONES) is a real time object detection algorithm available. Normally, YOLO has been trained for 80 objects using `darknet` dataset. And, we can use transfer learning methods to train YOLO for custom object detection. In this study we have used benchmark malaria dataset to train YOLO to detect malaria parasites.

> In addition to the transfer learning approach, I have done some modification to the original YOLO V4 algorithm so that I can perform better with cell detections. It will be available in the `darknet repository` when the PR is approved.

The original YOLO V4 algorithm is available in the [Darknet Respository](https://github.com/pjreddie/darknet) and you can learn more about YOLO (including internal architecture) using [Darknet Website](https://pjreddie.com/darknet/yolo/)

## Preparing the Dataset (Malaria / Leishamaniasis)
Dataset preparation includes several steps

1. ### Annotate the dataset 

In order to annotate images for YOLO, we user an image labeling tool called `LabelImg`. You can download the application using [this link](https://tzutalin.github.io/labelImg/) for Windows and Linux machines and using [this](https://github.com/tzutalin/labelImg#macOS).

Here are some of the video tutorials for labeling.
  - https://www.youtube.com/watch?v=VAgEF6Dxsy4 
  - https://www.youtube.com/watch?v=zSda1AoUTkc

> After annotating place all the images and their annotation files into a single folder (images) and zip (images.zip)

2. ### Training YOLO online

Since we need a GPU to train YOLO, we will be using `Google Colaboratory` for training.

  - Copy the images.zip file to malaria-detection-using-yolo folder and upload to the google drive and open `Train_YoloV3 .ipynb` file.

  - Go to `Edit` > `Notebook Settings`  and Select `GPU` under **Hardware Accelerators**. Click save.

  - Connect your google drive with Colaboratory

  - Run the notebook

> You might get different errors. Check the configurations and run the notebook again.

3. ### Detecting Parasites in Test Images

The weights of the trained algorithm will be saved in the google drive by the name `yolov3_training_last.weights`. 

  - Download it and paste inside `yolo_test_detection` folder.

  - Open `malaria_detection.py` and provide the path of the test image in line 14. and Run the script. You will be able to see the prediction.

> Sample predictions are available in the prediction folder. 