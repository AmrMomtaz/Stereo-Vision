# Stereo-Vision

## Description

I've implemented simple stereo algorithms. Given two images left and right and it is required to compute the horizontal disparity (ie., shift) of pixels along each scanline.<br>
This is the so-called baseline stereocase, where the images are taken with a forward-facing camera, and the translation between cameras is along the horizontal axis. I've computed the disparity using block matching by matching each pixel in the left image to a pixel in the right image.<br>
Since there is no rectification needed, I only needed to match the row in the left image with its equivalent in the right image. I've calculated the disparity in two ways, once using the cost as the Sum of Absolute Differences (SAD) and another time using Sum of Squared Differences (SSD).<br>
I've used different windows of size w where w = 1, 5 and 9 and I produced 6 maps: 2 maps for each window size, once using SAD and the other using SSD.

## Steps & Outputs

1) Loaded all the images in grey mode:<br>

![image](https://user-images.githubusercontent.com/61145262/206900241-80fe539f-3a15-4ff4-8eb3-faa1b874d245.png)

2) Performed the block matching algorithm by creating a function which takes parameters the window size, a boolean which determines whether to use the SAD or SSD and the left and right images. The algorithm is that we fix a template in the left image and we get from the right image all the boxes on the same line and the box which has the smallest distance using the loss function will be matched with the template and the disparity is calculated using this pixel and its corresponding one in the template. Here is the output of the images provided:<br><br>
**First Image:**<br><br>
![image](https://user-images.githubusercontent.com/61145262/206900333-61274fc5-3c50-434a-87d0-91384cf41214.png)<br><br>
  **Second Image:**<br><br>
![image](https://user-images.githubusercontent.com/61145262/206900369-a228d251-f18d-4dd6-b879-dc371aa2c65f.png)<br><br>
**Third Image:**<br><br>
![image](https://user-images.githubusercontent.com/61145262/206900434-65466ace-ab14-4734-9efc-b9e7464becd8.png)<br><br>
