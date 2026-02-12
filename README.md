# weapon-detection-yolov8-dip
Weapon-detection system using YOLOv8 and image-enhancement techniques.

A computer-based project that identifies both Weapons and humans using image processing techniques (DIP) that can improve the performance of a deep learning model under difficult lighting conditions.

## My method
Instead of just sending the images directly to YOLO, I developed a small image cleaning pipeline to assist with the reliability of YOLO's performance:

1.  **DIP Preprocessing:** * Applied **Contrast Limited Adaptive Histogram Equalization (CLAHE)** method to improve the contrast of each photo, specifically benefiting the shadow areas of each photo.
 * Applied a **Sharpening (Laplacian)** filter to provide better edge detection so that the outline of the weapons will appear more defined.

2. **Data Augmentation:** * The original size of the training set was small, so I developed Python code that allowed me to rotate, flip, and zoom in all of the photos.

3. **Training:** * Training the model on the **YOLOV8s** (small) model.
    * Using the **AdamW** optimizer
    * Image Size – examines **224x224** pixels.

## Results

My findings show that the CLAHE and Sharpening methods were necessary for identifying characteristics associated with weapons from an image. The model classified the images with a 66.6% confidence level for the human category. A 3.5% correct identification of weapons in the weapon category was established as the basis for future successful identification of weapons, given these challenges of low-resolution input from images and difficulties related to the detection of small objects. The established pipeline can serve as an effective starting point for additional work.

## Samples
<img width="2400" height="1200" alt="results" src="https://github.com/user-attachments/assets/fbcae0f1-fc1f-4b69-96c5-f6beb62217c4" />

![val_batch2_labels](https://github.com/user-attachments/assets/1e16f9f9-7733-43ff-8f34-2aca6e951e41)

## Project Organization

* The main programming code is maintained in the file **DIP_Project.ipynb** (pipeline for preprocessing and training).
* The Yolov8 configuration file is maintained in the **data.yaml** file.

## How To Run

1. First, install all of your requirement files: **pip install ultralytics opencv-python**
2. Finally, run the script file by executing **DIP_Project.ipynb**
