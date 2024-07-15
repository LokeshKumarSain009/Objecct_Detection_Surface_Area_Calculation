# Object Detection and Surface Area Calculation

## Overview

This project utilizes YOLOv4, OpenCV, and Python to detect objects in images, classify them as either rectangles or circles based on their aspect ratio, calculate their surface area, and visualize the results. The main objective is to demonstrate basic object detection capabilities and perform geometric calculations on detected objects.

## Files Included

1. **object_detection_surface_area.py**: Python script for performing object detection, shape classification, surface area calculation, and visualization using YOLOv4, OpenCV, and Matplotlib.
   
2. **sample_input_image.jpg**: Sample input image used in the project for testing purposes.
   
3. **README.md**: This file, providing an overview and explanation of the project.

## Dependencies

- Python 3.x
- OpenCV (`cv2` module)
- NumPy (`numpy` module)
- Matplotlib (`matplotlib.pyplot` module)
- YOLOv4 weights (`yolov4.weights`) and configuration file (`yolov4.cfg`)

## Approach

### Object Detection

1. **Loading YOLOv4 Model**: The YOLOv4 model is loaded using `cv2.dnn.readNet()` with pre-trained weights and configuration files.

2. **Loading Classes**: The COCO dataset classes are loaded from `coco.names`.

3. **Setting Up Layers**: Extracting output layers and layer names from the YOLOv4 network.

4. **Processing Image**: Reading and resizing the input image, converting it into a blob, and setting it as the input to the network.

5. **Forward Pass**: Running a forward pass through the network to detect objects in the image. Objects with confidence scores above a threshold are considered.

### Shape Classification and Surface Area Calculation

1. **Iterating Through Detection Outputs**: Extracting class IDs, confidence scores, and bounding box coordinates from the YOLOv4 output.

2. **Determining Shape**: Classifying detected objects as either rectangles or circles based on their aspect ratio (`w / h` ratio).

3. **Surface Area Calculation**: Calculating the surface area based on the detected shape:
   - For rectangles: \( \text{Area} = \text{width} \times \text{height} \)
   - For circles: \( \text{Area} = \pi \times \left(\frac{\text{width}}{2}\right)^2 \)

### Visualization

1. **Drawing Bounding Boxes**: Drawing bounding boxes around detected objects on the input image using OpenCV.

2. **Adding Labels**: Adding labels to the image indicating the object label, detected shape, and calculated surface area.

3. **Displaying Results**: Converting the image to RGB format (required by Matplotlib), displaying the annotated image using Matplotlib.

## Usage

1. Ensure all dependencies are installed (`cv2`, `numpy`, `matplotlib`).

2. Place the YOLOv4 weights (`yolov4.weights`), configuration file (`yolov4.cfg`), and class names file (`coco.names`) in the same directory as the script.

3. Run the script `object_detection_surface_area.py` with a sample input image or provide your own image path.

4. View the annotated image with detected objects, their shapes, and surface areas displayed.

## Future Enhancements

- **Real-Time Object Detection**: Modify the script to perform real-time object detection using video streams or webcams.
  
- **Additional Shape Recognition**: Expand shape classification to include more geometric shapes (e.g., triangles, ellipses).

- **Depth-Aware Surface Area Calculation**: Develop methods to estimate the actual physical surface area of 3D objects based on depth information.
