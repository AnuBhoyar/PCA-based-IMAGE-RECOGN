# PCA-based-IMAGE-RECOGN

Problem statement: Use PCA-based features and a k-Nearest Neighbor classifier to classify the
certainty that there is a volcano in the picture from the Volcanoes on UCI Venus image dataset. To make
this problem easier you can pre-process the images by cropping them around the indicated center of the
entity into a smaller size.

<b>Dataset Link : </b> https://www.kaggle.com/datasets/fmena14/volcanoesvenus

Dataset: I used Volcanoes on Venus dataset from Kaggle.com. It has total 9734 images. Image size
is 110 x 110. Training data set has 7000 images and test dataset has 2734 images. Images contains both
volcano and no volcano.

<img width="908" alt="image" src="https://user-images.githubusercontent.com/80166542/184410855-7adc5aec-758e-40d8-86ff-ca031a4ba774.png">

Total images with volcano in training dataset:1000
Total images with no volcano in training dataset:6000
Total images with volcano in test data set :434
Total images with no volcano in test data set :2300


Label file has 4 columns,
• Volcano? : if in the image there are volcanoes, 1 or 0.
for Volcano?=0 this three next features are NaN
• Type: 1= definitely a volcano,2 =probably, 3= possibly, 4= only a pit is visible
• Radius: is the radius of the volcan in the center of the image, in pixels
• Number Volcanoes: The number of volcanoes in the image

<img width="1207" alt="image" src="https://user-images.githubusercontent.com/80166542/184411047-e0d5ca2a-cea6-4066-a851-881f782c81be.png">

<b>Steps followed: </b>

1.At first, I took training dataset of 7000 images and passed that to PCA algorithm to get image
compressed that is to reduce dimensionality. I have passed different PCA components from 2 to
50 and then passed this PCA output to KNN algorithm and calculated accuracy for different k
values like 3,5,7,10,20,35,50.
As I increase PCA components I saw accuracy was increasing but as soon as I reached till
PCA component 35 accuracy was almost same. I checked till PCA component till 50.
Below is output for the same.

<img width="1172" alt="image" src="https://user-images.githubusercontent.com/80166542/184411400-e44069ab-5e32-437e-8471-54596f290ba9.png">

2. I took whole test data which has 2734 images & checked if image has volcano or not. I used PCA
component 35 as with PCA component 35 accuracy was good. So, on test data with 2 labels volcano or no
volcano, I got best accuracy for K=20. On average accuracy was 80% for test data.

<img width="1122" alt="image" src="https://user-images.githubusercontent.com/80166542/184411463-9035e911-69c5-490b-be1e-13400ac2eb23.png">

3. I took same whole test dataset and checked for label if volcano is there then what are chances that it is
defiantly volcano or probably volcano or possibly volcano or it’s a pit. (Type: 1= definitely a volcano,2
=probably, 3= possibly, 4= only a pit is visible). With PCA component 35 I got below accuracy for KNN.

<img width="1098" alt="image" src="https://user-images.githubusercontent.com/80166542/184411529-9c175f93-3fa1-4e08-90f4-fc577e812d20.png">

4.At last I just took data which has volcanoes only and checked for 4 classes. (Type: 1= definitely a
volcano,2 =probably, 3= possibly, 4= only a pit is visible). With PCA component 35 I got below accuracy
for KNN.Here Accuracy is reduced because I am using only volcano present images.

<img width="1117" alt="image" src="https://user-images.githubusercontent.com/80166542/184411608-6eaee330-08a0-473c-b75b-60fdb9a8bc35.png">





