# YOLOv3-aerial-photos
A model for object detaction using You Only Look Once v3 algorithm.

1. Download and unpack the main branch.
2. Download the ***yolov3_optimized_best.weights*** file from [https://drive.google.com/drive/folders/13C6JMyisoz3wDDdhj_85AeGnWgspQyTI](https://drive.google.com/drive/folders/1GaYrD8bOkUA5qKdBtFWwYkWyZTN7gxBs?usp=sharing)  and place it inside the YOLOv3-aerial-photos-main folder.
   The google drive also contains all the files used to train the model, including Jupyter Notebook with adequate commands.
4. Run Object_Detection.py and select the photo that you want to test the model on.


The goal of the project was to implement an algorithm for recognizing objects in aerial photographs. The yoloV3 algorithm was chosen for detection.
To create this tool, the ***Darknet*** neural network framwork was used, allowing to train the custom model based on the pre-trained model (with modifications including the go-to classes).

The first step to constructing the model was to prepare a set of annotated aerial photographs along with annotations denoting where in the image the objects are located.
The annotations were made by students for the purpose of the Laboratories. It was then necessary to convert COCO files with a .json extension corresponding to the annotations of several photos into files of YOLO format with a .txt extension.

 
 - An example of an aerial photograph with annotations corresponding to 11 following classes;
Budynek(**Building**), Drzewo(**Tree**), Pojazd(**Car**), WieleDrzew (**Many trees**), Cienie drzew(**Shadows of trees**), Skladowisko(**Junkyard**), Parking, PryzmaZiemi(**a Heap**), Wykop(**a Pit**), ZbiornikWodny (**Water Reservoir**), ParkingPolny (**Field Parking**) :<br>

<p align="left">
  <img src="https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/71b11590-0754-494e-8d3a-12c8efa8f3ce">
</p>
<sup> An annotated photo </sup>

##

 - An example of a YOLO Darknet format used to determine position of objects on the photographs:<br>
<p align="left">
  <img src="https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/0d36b7c6-f68a-46ec-b1dd-92fcd2102730">
</p>
<sup> 1st coulmn - class of object, 2-5 columns - location of bounding boxes </sup>

##
Google Drive and Google Colab services were used to train the model. Colab allows to use computing power from Google's graphic card. A repository contatining Darknet tool was cloned and the photographs, alongside the annotations were placed Google Drive. A total of 353 images were used.

The photos were split into sets - training (85%) and validation (15%).
Training parameters set accordingly to the YOLO authors' suggestions, with lower number of iterations:

![image](https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/d6600050-9927-4fe4-8ea2-6c9ea24edd59)<br>
<sup> Training parateters </sup>
##
The training was done many times, each time tweaking the parameters. The best .weights file reached 61,69% mean average precision. The results for each class were as follows:

![image](https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/aa65dc4c-7f87-4e53-8920-0cfbbc8a6b05) 

<sup> Best training results </sup>
##
![image](https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/e71d7a58-ddcc-40ae-9ffe-34863b6e4661)

<sup> Training graph </sup>
##
![image](https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/30259eeb-ebf7-4d8b-8e55-1541b6f491f5)

<sup> An example of detection on a photograph not used to train the model </sup>
