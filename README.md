# Estimate-Child-and-Person-Heights-from-images-or-Videos


This project aims to estimate the height of persons in an image by utilizing a combination of computer vision techniques including MCMT (Multi-Class Multi-Task) for eye detection and YOLO (You Only Look Once) for person detection. 

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Methodology](#methodology)
4. [Potential Errors](#potential_errors)
6. [Results](#results)
7. [Future Works and Improvements](#future_work_and_improvements)
8. [License](#license)

## Introduction
This repository contains code to estimate the height of individuals in an image. The process involves detecting the eyes of each person in the image and then calculating the height using a specific formula based on the distance between the eyes.

## Prerequisites
Before you begin, ensure you have met the following requirements:
- Python 3.11.7
- Pre-trained MTCNN model for eye detection
- Pre-trained YOLO model for person detection

## Methodology
The height estimation process involves several steps:

1. **Input Image**: The input is an image containing one or more persons.
2. **Eye Detection**: The MTCNN model is used to detect and extract the coordinates of the eyes for each person in the image.
3. **Person Detection**: The YOLO model detects the bounding boxes of each person in the image.
4. **Mapping Eye Coordinates to Bounding Boxes**: Each detected eye coordinate is mapped to its corresponding bounding box.
5. **Height Calculation**: The height of each person is calculated using the formula:
    ```
    Height = (6.3 * Height of Bounding Box in Pixels) / Distance between the Centers of the Two Eyes in Pixels
    ```
    where 6.3 cm is the approximate distance between the centers of the two eyes for an average human.

## Potential Errors and Limitations

While the method aims to estimate human height accurately, there are certain scenarios that may affect the reliability of the results:

1. **Person Facing Away**: If a person has their back to the camera, the MTCNN model may not detect their eyes, thus preventing height calculation for that individual.

2. **Large Movement**: If a person is jumping, or taking large strides while walking, their bounding box may be larger than normal. This can lead to an overestimation of their height due to the increased pixel dimensions of the bounding box.

It's important to consider these factors when interpreting the height estimation results from this system.


## Results
The output of the script will display the estimated heights of the persons detected in the input image.

## Future Works and Improvements

In future iterations of this project, we plan to explore the following enhancements:

1. **Improved Eye Detection**: Instead of relying on MTCNN for eye extraction, we aim to implement a depth-based model to predict the pixel distances between eyes directly from the image. This approach would be less dependent on the person's orientation relative to the camera.

2. **Enhanced Robustness**: Implementing robust techniques to handle scenarios where persons are not facing the camera or are in dynamic poses (e.g., jumping or large movements). This could involve integrating more sophisticated person detection and tracking algorithms.

3. **Depth Perception Integration**: Integrating depth perception techniques or depth sensors to accurately estimate the physical dimensions of persons in the image, thereby improving height calculations.

4. **Machine Learning Refinement**: Continuously refining machine learning models used for eye detection and person recognition to enhance accuracy and adaptability across diverse real-world scenarios.

These improvements aim to make the height estimation process more reliable and applicable in various practical settings.


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

