# SLT

The project focuses on translating American Sign Language (ASL). Transfer learning to extract features, followed by a custom classification block to classify letters. This model is then implemented in a real-time system with OpenCV - reading frames from a web camera and classifying them frame-by-frame. This repository contains the code & weights for classifying the American Sign Language (ASL) alphabet in real-time.

# Usage 

The entire pipeline is web camera -> image crop -> pre-processing -> classification.

The script loads a pre-trained model ([VGG16]/[ResNet50]/[MobileNet] with a custom classification block, and classifies the ASL alphabet frame-by-frame in real-time. The script will access web camera and open up a window with the live camera feed. A rectangular region of interest (ROI) is shown on the camera feed. This ROI is cropped and passed to the classifier, which returns the top 3 predictions. The largest letter shown is the top prediction, and the bottom 2 letters are the second (left) and third (right) most probable predictions. The architecture of the classification block will be described further in Sections 4/5.

## Dependencies
- OpenCV 3.1.0
- Keras 2.0.8
- tensorflow 1.11 (cpu version), it will also run with the gpu-version
- numpy 1.15.2
- joblib 0.10.3
