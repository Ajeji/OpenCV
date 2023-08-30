# Animal-Species-Detection
Roadkill is one of the highest causes of wildlife mortality and is of global conservation concern. Roadkill is an animal or animals that have been struck and killed by drivers of motor vehicles. In the United States, over 1 million vertebrate animals are killed by vehicle collisions every day. Globally, the number amounts to roughly 5.5 million killed per day, which when extrapolated climbs to over 2 billion annually. In Pilanesberg National Park many zebras and leopards are killed by car accidents each year. 
A New Study has identified globally some animal populations that are the most vulnerable to extinction in the next 50 years if observed roadkill levels persist. Mainly these animals include Leopard (83% increased risk of extinction from roadkill), wolf of Brazil (34% increased risk of extinction), cat of Brazil (increased extinction risk ranging from 0 to 75%), hyena of Southern Africa (increased extinction risk ranging from 0 to 75%).
The Wildlife Vehicle Collision (WVC) not only poses threat to animal safety but can cause injury to, or death of, vehicle occupants and vehicle damage. To mitigate the damage caused by these collisions, actions must be taken by the Department of Road like fencing highways, building wildlife crossings, escape routes, using high beam headlights by vehicles during night, and animal sensors in vehicles or alongside highways are some of the safety measures that can be incorporated to ensure safety of wildlife and humans alike.

## PROBLEM STATEMENT
This project seeks to develop an effective computer vision model using Deep Learning algorithm that can be deployed as part of detection systems to detect wildlife in urban environments, on highways using real-time visuals to warn humans of potential collision with wildlife.

## DATA PREPARATION

### DATA COLLECTION 
* Dataset 1: This is the Dataset of the previous cohort of interns. It was obtained from Kaggle, open source data inventory. It contains images of 4 species of animals. The dataset also contains text files containing annotations per image file in YOLO format. This dataset can be accessed here:
https://www.kaggle.com/datasets/biancaferreira/african-wildlife

* Dataset 2: This dataset was provided by Hamoye and directed to kaggle website. It contained images of 11 species of animals. However this dataset had no text files containing annotations and most of the images have low resolution. This dataset can be accessed here:
https://www.kaggle.com/datasets/brsdincer/danger-of-extinction-animal-image-set

* Dataset 3: This is the additional dataset, we obtained from Kaggle, containing images of 80 species of animals. The dataset has text files containing annotations in Pascal format and high-resolution images. This dataset can be accessed here:
https://www.kaggle.com/datasets/antoreepjana/animals-detection-images-dataset

## DATA PREPROCESSING
* Low to High Resolution: Many images in dataset 2 have low image resolution of approx. 250 pixels. Only high-resolution images from Dataset 2 were selected.
* Annotation: The high-resolution images selected from dataset 2 were annotated using the Make sense tool, as the model needs annotated images to be trained on. Also changing the annotation of images of only those classes in dataset 3 that are present in dataset 2, from Pascal format to YOLO format was done.
* Removing inappropriate data: Most of the images found in the leopard class contained other classes. Hence leopard class was dropped. 
Additionally, we added Tiger class from dataset 3.

## DATA EXPLORATORY ANALYSIS
After preprocessing the data, the dataset consists of 10 species of animals including zebras, rhinos, pandas, lions, elephants, buffalos, foxes, tigers, cheetahs, and jaguars. It comprises of total 2609 images along with text files containing annotations per image.

### Species of Animals taken into account

![Project Dataset](./figure/img1.png)

### Number of Images 

![Project Dataset](./figure/img2.png)

### Number of Images per class

![Project Dataset](./figure/img3.png)

![Project Dataset](./figure/img4.png)
 
## MODELLING 
Deep learning algorithm, You Only Look Once (YOLO) is used to build animal detection model. Precisely we have used YOLOv8. The YOLOv8 model is faster and more accurate while providing a unified framework for training models for performing Object Detection, Instance Segmentation, and Image Classification. The YOLO model directly predicts bounding boxes and class probabilities with a single network in a single evaluation. The simplicity of the YOLO model allows real-time predictions.

The Dataset was split into train, validation and test sets in the ratio of 0.7, 0.15, 0.15 respectively.

Yolov8 was implemented using command-line interface by installing ultralytics package. To build a new model , pre-trained weights were used with task argument as detect , mode as train , model as yolov8n . The model was trained for 50 epochs.



## EVALUATION
The performance of the object detection algorithm is evaluated by metrics such as Precision Recall Curve (PR Curve), Mean Average Precision (mAP) and confusion matrix.

### PR CURVE

![Project Evaluation](./figure/PR_curve_img5.png)
 
Mean Average precision is 0.965 across all classes at 0.5 threshold , which is good. 

### CONFUSION MATRIX

![Project Evaluation](./figure/norm_img6.png)
 
## MODEL DEPLOYMENT
The model was deployed using Streamlit on Hugging face. Streamlit is an open-source app framework.
- you can access the deployed [web app](https://huggingface.co/spaces/ldebele/animal_detection_app)

## CONCLUSION & RECOMMENDATIONS
Roads are essential infrastructure that connect people and circulate supplies but when they intersect with nature, the impact to species survival can be deadly. The model can be fed with real time images of highways to generate a prediction and thereby trigger sensors/alarms on highways or in vehicle to warn drivers of presence of predicted object on highways. The Model can also be used in fields of education and agriculture. 
