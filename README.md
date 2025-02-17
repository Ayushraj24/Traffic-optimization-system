# Traffic-optimization-system

# Vehicle Counter with YOLOv8

This project implements a vehicle counting system using YOLOv8 object detection and SORT tracking algorithm. The system can detect and count vehicles passing through a predefined line in a video stream.

## Features

- Real-time vehicle detection using YOLOv8
- Vehicle tracking using SORT algorithm
- Counting vehicles crossing a specified line
- Support for multiple vehicle classes (car, truck, bus, motorbike)
- Visual feedback with bounding boxes and counting display

## Prerequisites

- Python 3.8 or higher
- OpenCV
- CUDA-capable GPU (recommended for better performance)

## Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd vehicle-counter
```

2. Create and activate a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install the required packages:
```bash
pip install ultralytics
pip install opencv-python
pip install cvzone
pip install numpy
```

4. Install SORT tracking:
```bash
pip install sort-tracker
```

## Project Structure

```
vehicle-counter/
├── Videos/
│   └── cars.mp4        # Input video file
├── YOLOweight/
│   └── yolov8n.pt      # YOLOv8 model weights
├── graphics.png        # Overlay graphics
├── main.py            # Main script
└── README.md          # This file
```

## Setup Instructions

1. Download the YOLOv8 weights:
   - Create a directory named `YOLOweight`
   - Download the YOLOv8n weights from the official Ultralytics repository
   - Place the weights file (`yolov8n.pt`) in the `YOLOweight` directory

2. Prepare your video:
   - Create a directory named `Videos`
   - Place your input video file (named `cars.mp4`) in the `Videos` directory

3. Prepare the graphics:
   - Place your overlay graphics file (`graphics.png`) in the root directory

## Usage

Run the main script:
```bash
python main.py
```

The program will:
1. Open the video stream
2. Detect vehicles using YOLOv8
3. Track vehicles using SORT
4. Count vehicles crossing the specified line
5. Display the results in real-time

## Configuration

You can modify these parameters in the code:

- Detection confidence threshold: Change `conf > 0.3` in the code
- Tracking parameters:
  ```python
  tracker = Sort(max_age=20, min_hits=3, iou_threshold=0.3)
  ```
- Counting line position:
  ```python
  limits = [400, 297, 673, 297]
  ```

## Supported Vehicle Classes

The system detects and counts:
- Cars
- Trucks
- Buses
- Motorbikes

## Troubleshooting

1. If you get import errors:
   - Ensure all dependencies are installed correctly
   - Check Python path settings
   - Verify virtual environment activation

2. If video doesn't open:
   - Check the video file path
   - Ensure video file format is supported
   - Verify OpenCV installation

3. If detection is not working:
   - Verify YOLOv8 weights file path
   - Check CUDA installation for GPU support
   - Adjust confidence threshold


- YOLOv8 by Ultralytics
- SORT (Simple Online and Realtime Tracking) algorithm
- OpenCV community
