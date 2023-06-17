## About

Data labeling is a time-consuming and expensive process. However, in today's world of big data, we have a huge amount of unlabelled data. Semi-supervised learning methods help us train ML models using large amounts of unlabelled and small amounts of labeled data. In this project, I trained a semi-supervised image classification model. 

## Dataset

We used an augmented version of [stl-10](https://cs.stanford.edu/~acoates/stl10/) dataset. The dataset can be downloaded [here](https://drive.google.com/drive/folders/1mSfvu0nmeSlRPXell1Y2nKZ-R7YJqHKQ?usp=sharing).
Our training set consists of 100 labeled images belonging to 10 classes, 10 for each class, and 50000 unlabeled images. The test set contains 10000 images.

## Method

I used a pre-trained [Swin Transformer](https://arxiv.org/abs/2103.14030) as the encoder. First, I performed the supervised learning using the labeled data. Later I used pseudo labeling using the trained model and added the unlabeled data to the training set with pseudo labels. For pseudo labeling, I used a batch of 2000 images, labeled it using the trained model, and then retrained the model for 3 epochs. I did this until all unlabeled data was labeled.

## Install dependencies
```
  conda create --name ssl python=3.9
  conda activate ssl
  pip install -r requirements.txt
```

## Training and inference

Run [Semi_Supervised_Learning.ipynb](https://github.com/raja-kumar/CSE-164-Computer-Vision/blob/main/Project/Semi_Supervised_Learning.ipynb)

To use the pre-trained model. Go to “Reproduce result using trained (saved) model” (at the bottom) in the notebook provided and change the checkpoint path and test dataset path. run the following cells to reproduce the results. Pre-trained checkpoint can be downloaded [here](https://drive.google.com/drive/folders/1JK4M5-fJl4eCtQZX95IVMli6WOrWEda_)
