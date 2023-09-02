Age and Gender Detection using OpenCV and Google Colab
---------------------------------------------------------
This repository provides a Python code example for performing age and gender detection on a webcam image captured in Google Colab. The code uses pre-trained deep learning models to estimate the age and gender of faces detected in the image.

Prerequisites
--------------------
Before using this code, make sure you have the following dependencies installed:

Python (>=3.6)
OpenCV (opencv-python)
NumPy (numpy)
Pillow (PIL)
Google Colab (for webcam access)

You can install these packages using the following command:
pip install opencv-python numpy Pillow


Getting Started
-----------------------------------
Clone this repository or download the code files to your local machine.

Open a Jupyter Notebook in Google Colab or a similar environment that supports webcam access.

Upload the following pre-trained model files to your Colab environment. You can do this by running the provided code:

# Downloading pretrained data and unzipping it
!gdown https://drive.google.com/uc?id=1_aDScOvBeBLCn_iv0oxSO8X1ySQpSbIS
!unzip modelNweight.zip


How to Use
------------
Import the necessary dependencies and pre-trained models as described above.

Use the provided JavaScript code to capture a photo from the webcam. This code will display a live webcam feed and allow you to click a "Capture" button to take a photo. The captured image will be saved as 'photo.jpg' in your Colab environment.

Pass the captured image to the age_gender_detector function, which will detect faces in the image, estimate their gender and age, and annotate the image with the results.

Display the annotated image using the cv2_imshow function to view the results.

You can run the entire code cell to capture a new photo and perform age and gender detection on it.

Code Explanation
----------------------------
js_to_image(js_reply): This function converts the base64-encoded image received from JavaScript into an OpenCV BGR image.

bbox_to_bytes(bbox_array): Converts an image with bounding boxes drawn around detected faces into a base64 image byte string for overlaying on the video stream.

take_photo(filename='photo.jpg', quality=0.8): Captures a photo from the webcam using JavaScript and saves it as 'photo.jpg'. It also detects faces in the captured image and draws bounding boxes around them.

getFaceBox(net, frame, conf_threshold=0.7): Uses a deep learning model to detect faces in an image and returns the image with bounding boxes around detected faces.

Loading pre-trained models for age and gender estimation using OpenCV's cv2.dnn.

age_gender_detector(frame): Performs age and gender detection on the input frame, annotates the frame with the estimated results, and returns the annotated frame.

Acknowledgments
-----------------
This code example uses pre-trained models for age and gender detection, which were trained on a large dataset. 
