# Object Detection App
![object_detector](https://github.com/user-attachments/assets/ca285a8e-0d03-4ffd-8bca-a4bd2c64c56d)


This is an Object Detection application built using Streamlit, OpenCV, and MediaPipe. The app allows users to upload an image, and it will detect objects in the image using a pre-trained model.

## Requirements

- Python 3.12.3
- Streamlit
- OpenCV
- NumPy
- MediaPipe

## Installation

1. Clone the repository:
    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

2. Install the required packages:
    ```sh
    pip install streamlit opencv-python-headless numpy mediapipe
    ```

3. Download the pre-trained model [efficientdet_lite0.tflite](http://_vscodecontentref_/0) and place it in the project directory.

## Usage

1. Run the Streamlit app:
    ```sh
    streamlit run Object_detection.py
    ```

2. Open your web browser and go to `http://localhost:8501`.

3. Upload an image (jpg, jpeg, or png) using the file uploader.

4. The app will display the uploaded image and the image with detected objects.

## File Structure

- [app.ipynb](http://_vscodecontentref_/1): Jupyter notebook used to create the [Object_detection.py](http://_vscodecontentref_/2) script.
- [efficientdet_lite0.tflite](http://_vscodecontentref_/3): Pre-trained model for object detection.
- [Object_detection.py](http://_vscodecontentref_/4): Main script for the Streamlit app.

## Code Overview

### Object Detection

The object detection functionality is implemented using MediaPipe's Object Detector. The model is loaded using the following code:

```python
base_options = python.BaseOptions(model_asset_path="efficientdet_lite0.tflite")
options = vision.ObjectDetectorOptions(base_options=base_options, score_threshold=0.5)
detector = vision.ObjectDetector.create_from_options(options)
