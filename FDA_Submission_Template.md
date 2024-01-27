# FDA  Submission

**Your Name:Nathan Standafer**

**Name of your Device:**
Pneumonia Detector 1,000,000

## Algorithm Description 

### 1. General Information

**Intended Use Statement:** 
This device is is used to assist a Radiologist in diagnosing pesumonia from xrays of a patient's chest. 

**Indications for Use:**
The device is to be used for prioritizing xrays for evaluation when diagnosing pneumonia. 

**Device Limitations:**
 The device is not to be used as a diagnosis tool, as it lacks the accuracy necessary to perform a diagnosis.

**Clinical Impact of Performance:**
Using the tool allows and xrays with the highest probability of a positive diagnsis of pneumonia to be evaluated first by a radiologist.  The brings down the average time for pneumonia-positive patients to receive a diagnosis and increases the average time for pneumonia-negative to recieve a diagnosis.  This allows pneumonia-positive patients to receive treatment faster than they would without the use of the tool.


### 2. Algorithm Design and Function

<< Insert Algorithm Flowchart >>

**DICOM Checking Steps:**


**Preprocessing Steps:**
Before being processed by the tool, xray images must:
 - Be resized to 224 x 244 pixels.
 - Have the values shifted so they have a mean of 0
 - Have an overall standard deviation of 1.

**CNN Architecture:**
The device uses a variation of the VGG16 image classification model.  The final layers of the model are removed, and replaced with two fully connected layers.  The existing laygers form teh pre-trained VGG167 model are frozen with the layers taht were added left unfrozen for training.  The output of the tool is a single value between 0 and 1 representing the probability that the given xray is pneumonia positive.

### 3. Algorithm Training

**Parameters:**
The AI model of the tool was trained using the following parameters.
* A Batch size of 16
* An Optimizer learning rate starting at 0.0001 and decreasing by a factor of 10 until the model effectively stops improving during training.
* The layers from the pre-trained VGG16 model were left frozen that remained unchanged during training.
* No Layers of the pre-existing architecture were fine-tuned
* Layers that were added to the model for classification were not frozen and were trained.

<< Insert algorithm training performance visualization >> 


<< Insert P-R curve >>

**Final Threshold and Explanation:**

### 4. Databases
 (For the below, include visualizations as they are useful and relevant)

**Description of Training Dataset:** 


**Description of Validation Dataset:** 


### 5. Ground Truth



### 6. FDA Validation Plan

**Patient Population Description for FDA Validation Dataset:**

**Ground Truth Acquisition Methodology:**

**Algorithm Performance Standard:**
