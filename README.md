# Estimate-Child-and-Person-Heights-from-images-or-Videos


This project aims to estimate the height of persons in an image by utilizing a combination of computer vision techniques including MCMT (Multi-Class Multi-Task) for eye detection and YOLO (You Only Look Once) for person detection. 

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Methodology](#methodology)
6. [Results](#results)
7. [Contributing](#contributing)
8. [License](#license)

## Introduction
This repository contains code to estimate the height of individuals in an image. The process involves detecting the eyes of each person in the image and then calculating the height using a specific formula based on the distance between the eyes.

## Prerequisites
Before you begin, ensure you have met the following requirements:
- Python 3.6 or later
- Required Python packages listed in `requirements.txt`
- Pre-trained MCMT model for eye detection
- Pre-trained YOLO model for person detection

## Installation
To install the required packages, run:
```bash
pip install -r requirements.txt

## Usage
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/human-height-estimation.git
    cd human-height-estimation
    ```

2. Ensure you have the pre-trained models placed in the appropriate directory as specified in your configuration.

3. Run the script:
    ```bash
    python main.py --input_image <path_to_image>
    ```

## Methodology
The height estimation process involves several steps:

1. **Input Image**: The input is an image containing one or more persons.
2. **Eye Detection**: The MCMT model is used to detect and extract the coordinates of the eyes for each person in the image.
3. **Person Detection**: The YOLO model detects the bounding boxes of each person in the image.
4. **Mapping Eye Coordinates to Bounding Boxes**: Each detected eye coordinate is mapped to its corresponding bounding box.
5. **Height Calculation**: The height of each person is calculated using the formula:
    ```
    Height = (6.3 * Height of Bounding Box in Pixels) / Distance between the Centers of the Two Eyes in Pixels
    ```
    where 6.3 cm is the approximate distance between the centers of the two eyes for an average human.

## Results
The output of the script will display the estimated heights of the persons detected in the input image.

## Contributing
If you want to contribute to this project, please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-foo`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some foo'`).
5. Push to the branch (`git push origin feature-foo`).
6. Create a new Pull Request.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

