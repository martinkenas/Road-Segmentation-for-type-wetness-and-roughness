# Road-Segmentation-for-type-wetness-and-roughness
A system for segmenting road surface type, condition (wetness), and roughness from images using YOLOv8. Bachelor's Thesis.

# Road Surface Segmentation System

This repository contains the project files for a Bachelor's Thesis on "A System for Image Segmentation of Road Surface Type, State and Roughness." The system is designed to analyze images and video streams to identify and classify road surfaces based on their type (e.g., asphalt, gravel, pavement), condition (e.g., dry, wet), and roughness (e.g., smooth, rough, very rough).

The core of the system utilizes **YOLOv8n segmentation models**, individually trained for four distinct tasks:
1.  Overall road surface detection.
2.  Road surface type segmentation.
3.  Road surface condition (wetness) segmentation.
4.  Road surface roughness segmentation.

## Repository Contents

* `/model_training_scripts`: Contains Python scripts used for training each of the YOLOv8n models, including data preprocessing and augmentation configurations.
* `/trained_models`: Includes the pre-trained YOLOv8n model weights (in `.pt` files)
* `/main_system`: Contains the main Python script(s) for running the integrated system on video files. This script loads the trained models to perform sequential road surface analysis and visualization.
* `README.md`: This file.

## System Overview

The system processes input video frames by first identifying the road surface. This extracted road area is then passed to three subsequent models that classify its type, condition (wetness), and roughness. The final output visualizes these classifications on the video.

## Key Features

* **Multi-Attribute Segmentation**: Identifies road type, condition (dry/wet), and roughness.
* **Real-Time Capable**: Designed with YOLOv8n for efficient processing, achieving 10-12 FPS on NVIDIA Jetson AGX Orin with INT8 quantized models.
* **Custom Dataset**: Trained on a custom-built dataset of 1387 annotated images captured under various conditions.
* **Modular Design**: Uses four distinct models that can be potentially updated or refined individually.

## Getting Started

Run the main script on Colab and when prompted upload the models and video file. 

PyTorch version: 2.6.0
CUDA version: 12.4 (cuda124)
