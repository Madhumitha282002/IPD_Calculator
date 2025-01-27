# IPD Calculator

## Problem Statement

Around 64% of the population regularly wears eyeglasses. Of this group, approximately 14.1% purchased eyeglasses online in 2020. Moreover, about 30% of these buyers used the internet to compare prices, explore various eyeglass styles, or identify the eye care professional (ECP) or retailer for later in-person purchases.
Given the prevalent use of the internet, it has become crucial to offer customers the ability to purchase eyeglasses online that can be accurately assessed and tested. While online markets have successfully addressed some challenges, precise IPD (Interpupillary Distance) measurements remain a significant gap. This project aims to develop a model that determines a person's IPD using image or video analysis, enhancing the online eyeglass shopping experience.

Solution
Using AI and ML, our app determines the IPD distance of a patient. The process involves the patient placing a credit card on their forehead and clicking a picture. The model then analyzes the image and outputs the IPD value in millimeters.

## Introduction

### What is IPD?
IPD stands for Interpupillary Distance, the distance between the centers of the pupils in the two eyes. Measured in millimeters, it is essential in optometry and ophthalmology for ensuring the optimal fit of eyeglasses, contact lenses, and other vision-correcting devices. The average adult IPD is around 58-68 mm, with children’s IPD typically smaller.

### Why is IPD Required?
IPD is crucial for proper binocular vision, ensuring both eyes focus on the same point and work efficiently together. Correct alignment of pupils with optical lenses is essential for clear vision and comfort. IPD is also vital for:
Viewing 3D images or movies. Virtual Reality (VR) and Augmented Reality (AR) applications to calibrate displays for an immersive experience.

### How is IPD Measured?
Pupilometer: Uses infrared light to detect pupils’ positions and calculates the distance.
Mirror Method: The individual uses a mirror and a ruler or tape to measure the distance between pupil reflections.
Comprehensive Eye Assessments by opticians or optometrists.

### Why Bring Technology?
While traditional methods provide accurate results, growing technological needs demand fast and accessible testing. By integrating technology, users can measure their IPD online, test frames, and order eyeglasses conveniently.
Working Principle of AI Model
Reference Object: Credit cards are globally standardized in size.
Pixel Per Millimeter (ppmm): The length of the credit card (in pixels) is used to calculate ppmm:
ppmm = Length in mm / Length measured in pixels

IPD Calculation:
IPD (in mm) = IPD (in pixels) * ppmm

Challenges include ensuring accurate credit card detection. Using models like ResNet-50, the accuracy of measurement improves significantly with a robust dataset.

## My Journey

I was introduced to this project by Mr. Santosh, the lead on credit card detection. Initially, I explored edge detection techniques, such as:
Canny Edge Detection
Monocular Depth Estimation
Shape Predictors (e.g., Haar Cascades, Hough Transform, VGG)

Early attempts yielded unsatisfactory results. Discussions with Mr. Santosh led me to refocus on the problem from an IPD measurement perspective. Collaborations with colleagues and ML enthusiasts provided valuable insights.

To train the model, I created a custom dataset by capturing and annotating images with consent. This dataset became the foundation for refining the model’s accuracy.

## Code

The code repository is available here. Key components include:
- detect_measure_cc.py: Detects and measures the credit card length. The ResNet-50 model was used. Key steps involve:
Annotating the dataset.
Training the model with TensorFlow's Object Detection API.
- ppmm_cc.py: Calculates pixel per millimeter (ppmm).
- ipd.py: Detects eyes using the Haar-Cascade algorithm. Calculates the distance between pupil centers (in pixels) and multiplies this by ppmm to determine IPD in millimeters.

## Conclusion
The primary challenge was accurate credit card detection, addressed using ResNet-50. The project's success relies on the quality and quantity of the dataset. A robust dataset ensures better training and results.

