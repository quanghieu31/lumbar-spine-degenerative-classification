## Goal

- Detect and classify lumbar degenarative spine (LSD) conditions using lumbar sping MR images
- More information, credits, and data are on the Kaggle competition [website](https://www.kaggle.com/competitions/rsna-2024-lumbar-spine-degenerative-classification).

The 5 conditions are

- Left Neural Foraminal Narrowing 
- Right Neural Foraminal Narrowing 
- Left Subarticular Stenosis 
- Right Subarticular Stenosis 
- Spinal Canal Stenosis 

For each condition, classify the 5 intervertebral disc levels (IDL) = location of the compression
- L1/L2
- L2/L3
- L3/L4
- L4/L5
- L5/S1

Classify how severe of compression of the spinal cord due to foramina/subarticular exit (severity score/level) weights
- Normal/mild = 1
- Moderate = 2
- Severe = 4

So, essentially, for each observation, we have 5*5=25 output variables, each of which needs to be classified as one of the 3 severity levels.

## Steps:

1. Conduct EDA to understand the data and distributions: [rsna-lumbar-eda.ipynb](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/rsna-lumbar-eda.ipynb)
2. Develop essential functions to deal with data like making metadata, showing images, and coordinating directories: [rsna-lumbar-keyfunctions.ipynb](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/rsna-lumbar-keyfunctions.ipynb)
3. Examine the coordination of pathology and look into several images given the previously built functions: [rsna-lumbar-imageprocessing-and-coordpathology.ipynb](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/rsna-lumbar-imageprocessing-and-coordpathology.ipynb)
4. Convert the DICOM images into PNG for convenience and select subsets of the images for training: [rsna-making-dataset-png.ipynb](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/rsna-making-dataset-png.ipynb)
5. Make Dataset, DataLoader, transformations, define a ResNet50 model and training loop on AdamW optimizer and cuda GPU T4x2: [rsna-training-resnet50-gpu.ipynb](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/rsna-training-resnet50-gpu.ipynb). I will add more details to this. I had such a great time to learn from other notebooks on how to handle the data/image processing problem that involves multiple outcome variables for 3-class classification.


## Some visual info:

- Left Neural Foraminal Narrowing 
- Right Neural Foraminal Narrowing 

5 intervertebral disc levels            |  Severity
:-------------------------:|:-------------------------:
![](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/static/Neural-Foraminal-Narrowing.png)  |  ![](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/static/Neural-Foraminal-Narrowing-Severity.png)

- Left Subarticular Stenosis 
- Right Subarticular Stenosis 

5 intervertebral disc levels            |  Severity
:-------------------------:|:-------------------------:
![](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/static/Subarticular-Stenosis.png)  |  ![](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/static/Subarticular-Stenosis-Severity.png)

- Spinal Canal Stenosis 

5 intervertebral disc levels            |  Severity
:-------------------------:|:-------------------------:
![](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/static/Canal-Stenosis.png)  |  ![](https://github.com/quanghieu31/lumbar-spine-degenerative-classification/blob/main/static/Canal-Stenosis-Severity.png)