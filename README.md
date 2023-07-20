# YOLOv3-aerial-photos
A model for object detaction using You Only Look Once v3 Algorithm.

1. Download and unpack the main branch.
2. Download the .weights file from https://drive.google.com/drive/folders/13C6JMyisoz3wDDdhj_85AeGnWgspQyTI.
3. Run Object_Detection.py and select the photo that you want to test the model on.


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

 - An example of a YOLO Darknet format used to determine position of objects on the photographs:<br>
<p align="left">
  <img src="https://github.com/adammichalek/YOLOv3-aerial-photos/assets/43831694/0d36b7c6-f68a-46ec-b1dd-92fcd2102730">
</p>
<sup> 1st coulmn - class of object, 2-5 columns - location of bounding boxes </sup>

Google Drive and Google Colab services were used to train the model. Colab allows to use computing power from Google's graphic card. A repository contatining Darknet tool was cloned and the photographs, alongside the annotations were placed Google Drive. A total of 353 images were used.

The photos were split into sets - training (85%) and validation (15%).
