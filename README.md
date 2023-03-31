# face-detector-p22089
Face detection by using haar-cascade Algorithms

In this Repository provide two colab that using python and openCV lib to detect face and evalute that

## Detect face from webcam:

In this Colab We're going to connect webcam to colab and create a image of our face, after that by using haar cascade algorithms draw a box around the detected faces.
I use this command to use haar cascade classifier:
```
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
```

source: [Haar Cascades](https://medium.com/analytics-vidhya/haar-cascades-explained-38210e57970d).

## Evaluate haar cascade classifier by IOU metric

In this Colab, first we are download wiki dataset from [this link](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/static/wiki.tar.gz).
We are using mat file from wiki dataset to find the truth box of face and find the location of image in dataset.
There are some images in dataset that not valid so that I skiped them.

We run a loop to find box of face from images in wiki dataset and evalute an IOU metric for each image in dataset.
at the end, we're generating an average IOU metric over all the images in the dataset.

I found the accuracy low and I think the reasons:
* Haar cascade defined a square box but truth box in mat file not
* wiki dataset is not a clean dataset

sources:
* Downlaod Datasets :[IMDB-WIKI](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/)
* [Measuring the accuracy](https://blog.mturk.com/tutorial-measuring-the-accuracy-of-bounding-box-image-annotations-from-mturk-ad3dfcdf8aa0)
