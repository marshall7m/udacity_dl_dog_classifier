[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/vgg16_model.png "VGG-16 Model Layers"
[image3]: ./images/vgg16_model_draw.png "VGG16 Model Figure"


## Description

This project involved two major components. The first component is indentifying if the input image includes a dog or human. To detect human faces, I used OpenCV's [Haar feature-based cascade classifiers](https://docs.opencv.org/trunk/d7/d8b/tutorial_py_face_detection.html). To detect if the input image is a dog, I used the VGG-16 pretrained classfier. For more information on the details of this process see the dog_app.ipynb in this repo. The second component is essentially the CNN models used to predict the canine breed of the input image. For this task I created a CNN architecture from scratch and used a pretrained VGG-16 model (see model architectures below). Finally to combine both of these component's, I created a simple dog application that takes the user's input image(s) and predict's if it's a dog or human and its most likely canine breed (even if it's a human!).


![Sample Output][image1]

## Architecture

CNN model from scratch:

`Net(
  (conv1): Conv2d(3, 32, kernel_size=(3, 3), stride=(2, 2), padding=(1, 1))
  
  (batch_n1): BatchNorm2d(32, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)
  
  (conv2): Conv2d(32, 64, kernel_size=(3, 3), stride=(2, 2), padding=(1, 1))
  
  (batch_n2): BatchNorm2d(64, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)
  
  (conv3): Conv2d(64, 128, kernel_size=(3, 3), stride=(2, 2), padding=(1, 1))
  
  (batch_n3): BatchNorm2d(128, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)
  
  (pool): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
  
  (fc1): Linear(in_features=1152, out_features=500, bias=True)
  
  (fc2): Linear(in_features=500, out_features=133, bias=True)
  
  (dropout): Dropout(p=0.3)
)`

VGG-16 Model:

`VGG(

(features): Sequential(

(0): Conv2d(3, 64, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(1): ReLU(inplace)

(2): Conv2d(64, 64, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(3): ReLU(inplace)

(4): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)

(5): Conv2d(64, 128, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(6): ReLU(inplace)

(7): Conv2d(128, 128, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(8): ReLU(inplace)

(9): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)

(10): Conv2d(128, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(11): ReLU(inplace)

(12): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(13): ReLU(inplace)

(14): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(15): ReLU(inplace)

(16): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)

(17): Conv2d(256, 512, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(18): ReLU(inplace)

(19): Conv2d(512, 512, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(20): ReLU(inplace)

(21): Conv2d(512, 512, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(22): ReLU(inplace)

(23): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)

(24): Conv2d(512, 512, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(25): ReLU(inplace)

(26): Conv2d(512, 512, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(27): ReLU(inplace)

(28): Conv2d(512, 512, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))

(29): ReLU(inplace)

(30): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
)

(classifier): Sequential(

(fc1): Linear(in_features=25088, out_features=256, bias=True)

(drop1): Dropout(p=0.3)

(fc2): Linear(in_features=256, out_features=133, bias=True)

(drop2): Dropout(p=0.3)

) )`

### Hyper-Parameters

## Results
