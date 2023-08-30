# Animal-Species-Detection
Roadkill is one of the highest causes of wildlife mortality and is of global conservation concern. Roadkill is an animal or animals that have been struck and killed by drivers of motor vehicles. In the United States, over 1 million vertebrate animals are killed by vehicle collisions every day. Globally, the number amounts to roughly 5.5 million killed per day, which when extrapolated climbs to over 2 billion annually. In Pilanesberg National Park many zebras and leopards are killed by car accidents each year. 
A New Study has identified globally some animal populations that are the most vulnerable to extinction in the next 50 years if observed roadkill levels persist. Mainly these animals include Leopard (83% increased risk of extinction from roadkill), wolf of Brazil (34% increased risk of extinction), cat of Brazil (increased extinction risk ranging from 0 to 75%), hyena of Southern Africa (increased extinction risk ranging from 0 to 75%).
The Wildlife Vehicle Collision (WVC) not only poses threat to animal safety but can cause injury to, or death of, vehicle occupants and vehicle damage. To mitigate the damage caused by these collisions, actions must be taken by the Department of Road like fencing highways, building wildlife crossings, escape routes, using high beam headlights by vehicles during night, and animal sensors in vehicles or alongside highways are some of the safety measures that can be incorporated to ensure safety of wildlife and humans alike.

# Table of Contents
- [Datasets](#datasets)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Evaluation](#Evaluation)
- [Web App](#web-app)
- [Contirbuting](#contributing)


## PROBLEM STATEMENT
This project seeks to develop an effective computer vision model using Deep Learning algorithm that can be deployed as part of detection systems to detect wildlife in urban environments, on highways using real-time visuals to warn humans of potential collision with wildlife.



## Datasets
* Dataset 1: It was obtained from Kaggle. It contains images of 4 species of animals. The dataset also contains text files containing annotations per image file in YOLO format. This dataset can be accessed [here](https://www.kaggle.com/datasets/biancaferreira/african-wildlife).

* Dataset 2: It contained images of 11 species of animals. However this dataset had no text files containing annotations and most of the images have low resolution. This dataset can be accessed [here](https://www.kaggle.com/datasets/brsdincer/danger-of-extinction-animal-image-set)

* Dataset 3: It obtained from Kaggle, containing images of 80 species of animals. The dataset has text files containing annotations in Pascal format. This dataset can be accessed [here](https://www.kaggle.com/datasets/antoreepjana/animals-detection-images-dataset)

## Project Structure
    ├── config
    │   └── custom.yaml
    ├── data
    │   ├── images
    │   ├── labels
    │   └── raw
    ├── doc
    │   ├── figure
    │   ├── Final Project Documentation.pdf
    │   ├── Final Research Article.pdf
    │   ├── README.md
    │   └── Team OpenCV Final project proposal..pdf
    ├── logs
    │   └── log.log
    ├── notebooks
    │   ├── EDA.ipynb
    │   └── yolov8.ipynb
    ├── runs
    │   └── detect
    │       ├── train
    │       └── val
    ├── scripts
    │   ├── app.py
    │   ├── convert_format.py
    │   └── train_test_split.py
    ├── test
    |   └── data.py
    ├── README.md
    └── requirements.txt

## Getting Started
Follow theses steps to set up the environment and run the application.
1. Fork the repository [here](https://github.com/ldebele/animal-Species-Detection).
2. Clone the forked repository.
    ```bash
    git clone https://github.com/<YOUR-USERNAME>/Animal-Species-Detection
    cd Animal-Species-Detection
    ```

3. Create a python virtual environment.
    ``` bash
    python3 -m venv venv
    ```

4. Activate the virtual environment.

    - On Linux and macOS
    ``` bash
    source venv/bin/activate
    ```
    - On Windows
    ``` bash
    venv\Scripts\activate
    ```

5. Install Dependencies
    ```bash
    pip install -r requirements.txt
    ```
6. Run the application.
    ```python
    streamlit run './scripts/app.py'
    ```
## Evaluation
The performance of the object detection algorithm is evaluated by metrics such as Precision Recall Curve (PR Curve), Mean Average Precision (mAP) and confusion matrix.

# PR CURVE

![Project Evaluation](https://github.com/Ajeji/OpenCV/blob/main/readme_img/img5.png?raw=true)
 
Mean Average precision is 0.965 across all classes at 0.5 threshold , which is good. 

## Web App
The model was deployed using Streamlit on Hugging face.
- you can access the deployed [web app](https://huggingface.co/spaces/ldebele/animal_detection_app)
