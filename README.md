# PreEmo(Facial Emotion Detector)
## Demo

![Real-time Emotion Detection]([assets/real-time-demo-1.jpg](https://circuitdigest.com/sites/default/files/projectimage_mic/Raspberry-Pi-Facial-Expression-Recognition.jpg))
*Example: Webcam detecting "happy" and "neutral" emotions*

# 📝Description

A computer vision system that analyzes facial expressions in images or real-time video to automatically classify human emotions (e.g., happy, sad, angry, surprised, neutral, fear, disgust).

**Supported emotions**: happy, sad, angry, surprised, neutral, fear, disgust  
**(7-class facial expression recognition)**

<p align="center">
  <img src="https://via.placeholder.com/800x400.png?text=Demo:+Real-time+Emotion+Detection" alt="Demo GIF" width="80%"/>
  <br>
  <em>Real-time emotion detection from webcam (example output)</em>
</p>

## ✨ Features

- Real-time facial emotion recognition using webcam
- Static image emotion prediction
- Face detection + emotion classification pipeline
- Support for multiple popular deep learning approaches:
  - Custom CNN trained from scratch
  - Transfer learning (VGG16 / ResNet50 / MobileNet)
  - Pre-trained models (DeepFace, FER library)
- Clean modular code structure
- Easy to train on FER-2013, AffectNet or custom datasets

# 🤖About the Models

The system employs two models: one for face detection and another for facial emotion classification.

## Face Detector

* Face detection model is built using TensorFlow 2.0 object detection API, where I used SSD MOBILENET V2 as the pretrained model.
* To built a face detection model first get the data(There will be many resources out there or else take some random pictures from internet and the number is dependent, in my case it's 50 for training and 10 for validation) to train the model.
* And then follow [this](https://tensorflow-object-detection-api-tutorial.readthedocs.io/) documentation to train a face detector on the gathered data. If u want a video tutorial check [this](https://youtu.be/XoMiveY_1Z4).
* I'd used colab to train the model.

## Facial Emotion Classifier

* Facial Emotion Classification model is built using TensorFlow 2.0, where I trained a deep convolutional neural network on RAF-DB. It's a generalised modelwith a training accuracy of 90% and test accuracy of 83%.
*  I'll create a separate repo on how to create a model like this, so if you're here then check my repos.
*  RAF-DB is a private database and to download it you need to send an email as shown on their [website](http://www.whdeng.cn/raf/model1.html#:~:text=Real%2Dworld%20Affective%20Faces%20Database%20(RAF%2DDB)%20is,labeled%20by%20about%2040%20annotators.).
*  First I'd started training the model on my local machine(GPU - GTX 1660ti), but when I started incresing the complexity of the model it took a lot of time to train and also started crying like a baby. 
*  I can't experiment fastly, So I shifted to kaggle to train the model. I've choosen kaggle over colab because of it's more gpu time and resources and it made experimentation faster.

## How it works

The input image is first given to the face detector to detect the face and then this is given to the facial emotion classifier to classify the emotion.

<p align="right">(<a href="#top">back to top</a>)</p>

# 🖥Installation

## 🛠Requirements

* Python 3.7+ 
* Other requirement are mentioned in requirements.txt and can be installed as shown below.

## Installation

bash

1. Clone the repository
---
git clone https://github.com/rohitchandra12/PreEmo.git
cd facial-emotion-detection
---
2. Create virtual environment (recommended)
---
python -m venv venv
source venv/bin/activate    # Linux/Mac
venv\Scripts\activate       # Windows
---

3. Upgrade pip to the latest version.
```
python -m pip install --upgrade pip
```
Clone the PreEmo repo and change the directory to EmoViz and run the below command.

# 4. Install dependencies
---
pip install -r requirements.txt
---
