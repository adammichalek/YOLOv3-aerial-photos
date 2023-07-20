# YOLOv3-aerial-photos
A model for object detaction using You Only Look Once v3 Algorithm.

1. Download and unpack the main branch.
2. Download the .weights file from https://drive.google.com/drive/folders/13C6JMyisoz3wDDdhj_85AeGnWgspQyTI.
   This file contains the file that the model has been trained on.
3. Run Object_Detection.py and select the photo that you want to test the model on.


The goal of the project was to implement an algorithm for recognizing objects in aerial photographs. The yoloV3 algorithm was chosen for detection.
To create this tool, the Darknet neural network framwork was used, allowing to train the custom model based on the pre-trained model (with modifications including the go-to classes).

The first step to constructing the model was to prepare a set of annotated aerial photographs along with annotations denoting where in the image the objects are located.
The annotations were made by students for the purpose of the Laboratories. It was then necessary to convert COCO files with a .json extension corresponding to the annotations of several photos into files of YOLO format with a .txt extension.

An example of an aerial photograph with annotations corresponding to 11 following classes:
Budynek(**Building), Drzewo(**Tree), Pojazd(**Car), WieleDrzew(**Many trees), Cienie drzew(**Shadows of trees), Skladowisko(**Junkyard), Parking, PryzmaZiemi(**a Heap), Wykop(**a Pit), ZbiornikWodny (**Water Reservoir), ParkingPolny (**Field Parking)

![image](https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/7802310e-3b41-4804-b9bd-52c12be1801d)


