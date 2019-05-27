[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/vgg16_model.png "VGG-16 Model Layers"
[image3]: ./images/vgg16_model_draw.png "VGG16 Model Figure"


## Description

This project involved two major components. The first component is indentifying if the input image includes a dog or human. To detect human faces, I used OpenCV's [Haar feature-based cascade classifiers](https://docs.opencv.org/trunk/d7/d8b/tutorial_py_face_detection.html). To detect if the input image is a dog, I used the VGG-16 pretrained classfier. For more information on the details of this process see the dog_app.ipynb in this repo. The second component is essentially the CNN models used to predict the canine breed of the input image. For this task I created a CNN architecture from scratch and used a pretrained VGG-16 model (see model architectures below). Lastly, to combine both of these component's, I created a simple dog application that takes the user's input image(s) and predict's if it's a dog or human and its most likely canine breed (even if it's a human!).


![Sample Output][image1]

## Architecture

### Hyper-Parameters

## Results
