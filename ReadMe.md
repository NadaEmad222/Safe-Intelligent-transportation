# Safe Intelligent Transportation Using AI in Smart Cities

The concept of Safe Intelligent transportation leverages technology advancements and AI to enhance the sustainability, efficacy, and security of urban transportation networks in Digital Cities. It involves integrating cutting-edge technologies with transportation infrastructure and vehicles to facilitate statistical analysis, real-time detections, and automated decision-making.

## Table of Contents
- [Motivation](#motivation)
- [Objective](#objective)
- [Pipeline](#pipeline)
- [Detailed Description](#Description)
- [Testing the Model](#Testing-the-Model)
- [File Structure](#file-structure)
- [Recommendations](#Recommendations-for-Further-Work)
- [Contribution](#contribution-guidelines)

## Motivation
Despite advancements in car safety and infrastructure, road accidents remain a leading cause of death among youth and young adults. This project seeks to improve urban living conditions and save lives by transforming road safety with AI.

## Objective
This project aims to develop a Neural Network (NN) model that predicts and detects road accidents before they occur. The model is designed to learn from video scenes and identify early-stage accident patterns, contributing significantly to the goal of zero road deaths through AI.

## Pipeline

The project follows a pipeline of
feature extraction → data preprocessing → accident prediction.

## Description 

we utilized the [car crash dataset (CCD)](https://github.com/Cogito2012/CarCrashDataset) for the analysis of accidents and non-accidents. In order to extract features from the videos within the dataset, the YOLOv9-e model from ultralytics was employed for object detection. It was observed that the model required fine-tuning specifically for the detection of transportation objects from a dashcam viewpoint to align with the objects present in the car crash dataset and to efficiently detect objects. The [vehicle orientation dataset](https://github.com/sekilab/VehicleOrientationDataset/tree/main) was utilized for the fine-tuning of the YOLOv9 model due to its inclusion of object orientations which served as a crucial feature for the model to learn motion patterns during the analysis of video frames. Subsequently, the YOLO model was employed to analyze the CCD videos and extract features and Data was preprocessed and organized into sequences for training the LSTM and GRU models, built using keras for early accident detection.

[The Paper](https://drive.google.com/file/d/1bM27C8xU2vcnycxYq7-rCQdZ30SUHuZe/view?usp=sharing)


## File Structure

Upon executing the code, the resulting file structure will be as follows:

```
📦 Safe_Intelligent_Transportation
|
├─ Notebook.py
|
├─ Inference.py
|
├─ Object_Detection_Dataset
|  ├─ data.yaml
|  ├─ test
|  │  ├─ images
|  │  └─ labels
|  ├─ train
|  │  ├─ images
|  │  └─ labels
|  └─ validate
|     ├─ images
|     └─ labels
|
├─ yolov9e.pt
|
├─ runs
|  └─ detect
|     └─ train
|        └─ weights
|           └─ best.pt
|
├─ Accident_Prediction_Dataset
|     ├─ accidents
|     └─ Non_accidents
|
├─ CCD_Accident_Sequences
|     ├─ train
|     └─ validate
|
├─ CCD_Normal_Sequences
|     ├─ train
|     └─ validate
|
├─ accident_prediction_LSTM_model.keras
|
├─ accident_prediction_GRU_model.keras
|
├─ historyLSTM.pickle
|
└─ historyGRU.pickle

```

## Recommendations for Further Work

These are some suggestions for future enhancements and contributions to elevate this project.

- Employ advanced techniques for data sampling from datasets to reduce class imbalance.

- Enhance feature detection and extraction from video frames and include new features such as (traffic lights, car backlights, and street lanes).

- Explore the application of Transformer models for prediction tasks due to their exceptional known performance in capturing long-range dependencies.

- Develop a multi-class accident categorization system that categorizes accidents based on various factors such as (high speed, weather conditions, and aggressive driving) and offers personalized driver recommendations instead of general warning.

These proposed directions underscore our commitment to refining our approach and enhancing model performance, contributing significantly to traffic safety solutions.


## Contribution guidelines

We welcome contributions  to further enhance this project's capabilities and reach its objectives more effectively. To contribute please follow the following steps :

1) Fork the Repository: Create a copy of the project to your GitHub account.
2) Clone the Fork: Download your forked repository to your local machine.
3) Create a New Branch: Make changes in a new branch, not in the main branch.
4) Make Your Changes: Add or edit files as needed for the contribution.
5) Commit Your Changes: Save your changes with a clear commit message.
6) Push to Your Fork: Upload your changes to your fork on GitHub.
7) Open a Pull Request: Propose your changes to the original project.
8) Discuss and Review: we will review it, and may discuss the changes.

If accepted, the Pull Request will Get Merged and your changes will be merged into the project.
