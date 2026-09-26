# Smart Traffic Analyzer

A deep learning-based traffic video analysis system that detects vehicle license plates, recognizes plate numbers using OCR, verifies repeated readings, filters duplicate vehicles, and generates a traffic log with video timestamps.

## Project Overview

Smart Traffic Analyzer analyzes a traffic video using YOLO-based license plate detection, EasyOCR, and OpenCV.

The system:

1. Reads a traffic video.
2. Detects license plates using YOLO.
3. Extracts the detected plate region.
4. Recognizes characters using EasyOCR.
5. Verifies plate readings across multiple frames.
6. Filters duplicate plate numbers.
7. Records the recognized plate and video time in a CSV file.
8. Generates an annotated output video with detection information.

## Features

- License plate detection using YOLO
- License plate character recognition using EasyOCR
- Traffic video processing using OpenCV
- Multi-frame verification of detected plates
- Duplicate vehicle filtering
- Video timestamp recording
- CSV-based traffic log
- Annotated video output
- Jupyter Notebook implementation

## Technologies Used

- Python
- OpenCV
- YOLO
- Ultralytics
- EasyOCR
- Pandas
- Matplotlib
- Jupyter Notebook

## Project Structure

Smart-Traffic-Analyzer/
│
├── Smart_Traffic_Analyzer.ipynb
├── README.md
├── requirements.txt
│
├── screenshots/
│   └── result.png
│
└── outputs/
    └── traffic_log.csv

## Setup

### 1. Clone the Repository

git clone https://github.com/divyasripathy/Smart-Traffic-Analyzer.git

cd Smart-Traffic-Analyzer

### 2. Install Required Libraries

pip install -r requirements.txt

The required packages are:

ultralytics
opencv-python
easyocr
pandas
matplotlib

### 3. Open the Notebook

Start Jupyter Notebook:

jupyter notebook

Open:

Smart_Traffic_Analyzer.ipynb

## Required Model Files

The project requires a YOLO model specifically trained for license plate detection.

The notebook uses a license-plate detection model and downloads the model automatically when the model-loading cell is executed.

Example:

from ultralytics import YOLO

plate_model = YOLO(
    "https://huggingface.co/Koushim/yolov8-license-plate-detection/resolve/main/best.pt"
)

The model file is not included in this repository because model weight files can be relatively large.

Important:

A normal YOLO object-detection model such as yolo11n.pt is not a replacement for the license plate detection model.

The project requires a model trained specifically to detect license plates.

## Input Video

Place the traffic video inside the input folder:

input/
└── traffic.mp4

The video should preferably contain:

- Clearly visible vehicles
- Visible license plates
- Good lighting
- Limited motion blur
- Plates visible across multiple frames

Large video files are intentionally not included in the GitHub repository.

## Usage

Run the cells in:

Smart_Traffic_Analyzer.ipynb

The main workflow is:

Traffic Video
      ↓
YOLO License Plate Detection
      ↓
Plate Extraction
      ↓
Image Preprocessing
      ↓
EasyOCR
      ↓
Multi-Frame Verification
      ↓
Duplicate Filtering
      ↓
Traffic Log + Annotated Video

## Output Files

### Annotated Video

The processed video is saved as:

outputs/annotated_traffic.mp4

The video contains:

- License plate bounding boxes
- Recognized plate text
- Video timestamp
- Unique vehicle count

### Traffic Log

The recognized vehicles are stored in:

outputs/traffic_log.csv

Example:

Video Time,Number Plate
00:03,106TI
00:08,TN01AB1234

The exact values depend on the input video and OCR results.

## Result Screenshot

A screenshot of the project result is available at:

screenshots/result.png

## Notes

- OCR accuracy depends on the quality, size, angle, and visibility of the license plate.
- Blurry or very small plates may not be recognized correctly.
- Multiple-frame verification is used to reduce incorrect single-frame OCR readings.
- The project is intended as a college-level prototype for traffic video analysis.
- Large input videos, output videos, and model weight files are excluded from the GitHub repository.

## Future Enhancements

Possible future improvements include:

- Real-time CCTV camera support
- Improved OCR accuracy
- Indian license plate-specific OCR preprocessing
- Vehicle type classification
- Speed estimation
- Vehicle tracking
- Database storage
- Web dashboard
- Traffic statistics and visualization

## Project Workflow

Input Traffic Video
        ↓
YOLO License Plate Detection
        ↓
License Plate Crop
        ↓
EasyOCR
        ↓
Multi-Frame Verification
        ↓
Duplicate Filtering
        ↓
Annotated Video + Traffic Log CSV

## Author

Divyasri Lakshmipathy

B.Tech Artificial Intelligence and Data Science

GitHub:
https://github.com/divyasripathy
