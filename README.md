# Today I Learned (TIL) 2021
The repository contains a Jupyter Notebook file used for the competition. 
The code is written on top of a baseline code provided by DSTA for the 
competitors.

The purpose of participating in the competition is to gain a better understanding
of DSAI and broaden my horizon on top of what my curriculum provides. Our team
(Uluntu20) managed to get into the <b>top 10</b> out of the entire competition:

![Leaderboard](https://github.com/xinweilau/TIL2021-CV/blob/master/Leaderboard.png)

## Learning Points
Below is a summary of what I have learned during these 2 days of the hackathon:

### 1. Additional image data to train
> During the competition, although we were provided with hundreds to thousands
> of images. After running the baseline model provided, the team achieved a 
> model accuracy of 0.59. Afterward, the team discovered the hidden easter egg
> which contained more images. The model had an increase in an accuracy rate of
> 0.61 after adding those hidden images. 
>  
> We were under the impression that we are only allowed to use the images 
> provided by DSTA. In hindsight, perhaps we should have sourced for 
> additional images for the model to train instead of purely relying on the 
> provided dataset and image augmentations.

### 2. Adjusting Hyper-Parameters and Google Colab Pro
> In the beginning, we went with the approach of adjusting the hyper-
> parameters such as batch size, number of epochs and number of workers, etc.
> However, these adjustments only produced limited improvement in prediction
> accuracy. An observation made was that the model starts to stagnate (or even
> decrease) in Active Prediction / Active Recall after a certain epoch. 
> Additionally, as the team was running the model on Google Colab free platform, 
> we had limited access to resources (e.g. GPU memory) for our training. 
> This is especially when trying to run the model multiple times under a single 
> session when the session would crash due to running out of resources. 
> 
> We eventually migrated to Google Colab Pro which provided access to more
> resources and computing capabilities. The overall time required to train the
> models which would take hours to complete now can be done at a fraction 
> of the time. The increase in resources also allowed us to utilise a neural
> network with more layers (e.g. from RESNET50 to RESNET152).
> 
> Another issue faced was that our computers need to stay in session while 
> the model is training. This resulted in a significant time spent waiting 
> for the model to train and test if the model improved.
>
> The competition comes with a $100 credit for Amazon Web Services. In hindsight,
> we should have utilised Amazon SageMaker to run our model such that we do not
> need to be restrained with having to constantly stay in session.

### 3. Image Data Augmentation
> One of the important learning lessons in this competition is the choice
> of proper image augmentation. As the team proceeds further into the challenges, 
> more characteristics are introduced into the dataset. For instance, the 
> rain effect was introduced in Challenge 3. It is important to determine the
> characteristics of the images on which the model will be tested on, and then
> to introduce corresponding image augmentations as this will lead to an 
> overall improvement in accuracy when running the test images.
> 
> One of the approaches to Image Augmentation utilised by the team was using 
> [Albumentations](https://github.com/albumentations-team/albumentations),
> a python library for image augmentation. The library provides many methods 
> which simplify the process of image augmentation by providing useful methods
> such as creating random rain introduced in challenge 3 while reducing the 
> amount of time required to perform image augmentation. This is in contrast to
> having to write a wrapper class for every PyTorch transformation.
> 
> As this is my first time using Computer Vision, I was not familiar with the 
> PyTorch library as well as the baseline code given to us. As I am still 
> inexperienced with computer vision, perhaps there are other augmentation
> methods that would help with the training of the data (or other techniques
> to improve the performance). A lot of time was needed having to re-train 
> the model in hopes of reaching a better accuracy.

## Conclusion
To conclude, I felt that our team did well granted that it was our first time
participating in such a competition. I have certainly expanded my horizons on
how to get started with doing Computer Vision using popular Deep Learning 
models such as RESNET for Image Recognition.

Moving on, I would like to try to learn more about hyper-parameters
and explore the best practices in fine-tuning these parameters. Furthermore, 
I would also like to explore different types of models architectures for 
Computer Visions beyond RESNET and techniques to improve the training accuracy
of the models such as ensemble learning. I would continue to explore and sharpen
my skill sets through online courses from Coursera, and to come back next 
year better prepared for the competition.