# Object-Detection-and-Caption-Generation-Project

This project integrates object detection and natural language generation to provide detailed, context-rich captions based on the objects detected in images. The pipeline uses **YOLO** for object detection and **Gemini** for generating captions.

## Requirements

To run the script, ensure that you have the following installed:

- `ultralytics`
- `supervision`
- `roboflow`
- `google-generativeai`
- `pandas`
- `os`

You can install these dependencies using pip:

```bash
%pip install ultralytics supervision roboflow google-generativeai pandas
```


# Steps to Run the Script
## Set up the environment:

Ensure that you have your images placed in the appropriate folder.
Set up your Google API key for accessing Gemini (Generative AI).

## Download the Pre-trained Models:

YOLO (You Only Look Once): This is a pre-trained object detection model used for detecting objects in images.
Gemini: A generative AI model used to generate detailed captions based on detected objects and optional keywords.
## Run the Script:

The script will process images, detect objects using the YOLO model, and generate captions based on these detected objects using the Gemini model.
The following steps are executed in the script:
Load YOLO model and run inference on images to detect objects.
Save the detected object labels in text files for each image.
Process each text file to extract object labels and pass them to the Gemini model to generate captions.
Optionally, a keyword can be added to modify the context of the caption.

## Example Command: After setting up the environment, simply run the script:

```bash
python task1.py
```

## Output:

The output will include generated captions for each image in the console, along with the caption text stored in separate files.

# Models Used
## YOLO (You Only Look Once)
Model: YOLO("yolo11s.pt")
Purpose: YOLO is a state-of-the-art object detection model that is capable of detecting objects in real-time. It is chosen for this project because of its speed, accuracy, and the fact that it is pretrained on large datasets (like COCO), making it a reliable choice for detecting common objects.
Why YOLO?: YOLO is effective at detecting multiple objects in images with high speed and accuracy. It performs well in real-time applications and handles various objects in a single pass, which is suitable for this task.

## Gemini (Google Generative AI)
Model: gemini-pro (via Google Generative AI API)
Purpose: Gemini is used to generate context-rich captions based on the object labels detected by YOLO.
Why Gemini?: Gemini is a powerful generative AI model that can generate detailed, natural language text based on structured data (such as the list of detected objects). It allows us to take raw object labels and generate informative, human-readable captions.
