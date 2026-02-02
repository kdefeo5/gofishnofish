# Go Fish No Fish

### Binary classification of images (fish / no fish) using CNN in Keras Tensorflow

In this project I'm using Kaggle's Blue Bot Fish No Fish dataset to build a CNN that classifies underwater images as 'contains fish' or 'does not contain fish'.

**Dataset:** [Blue Bot Fish/No Fish Dataset](https://www.kaggle.com/datasets/hiyaro/doesimagehavefish) on Kaggle

## Problem

Say a marine biologist is given a data set with images to identify and count fish, but only half the images actually contain fish and they're unlabeled. They can save time by classifying images into a "contains fish" category and avoid combing through images that don't have fish for them to identify.

## Results

The improved model (with data augmentation and dropout) achieved ~91% validation accuracy, compared to ~87% with my original model that didn't have proper preprocessing.

## What's in this repo

- `gofishnofish.ipynb` - Main notebook with both models and analysis
- `requirements.txt` - Python dependencies
- `README.md` - This file

## Running the notebook

### On Kaggle 
1. Go to the [dataset page](https://www.kaggle.com/datasets/hiyaro/doesimagehavefish)
2. Click "New Notebook"
3. Copy the code from `gofishnofish.ipynb`

### Locally
```bash
pip install -r requirements.txt
jupyter notebook gofishnofish.ipynb
```

You'll need to download the dataset from Kaggle and update the `DATA_DIR` path.

## References

- [TensorFlow Image Classification Tutorial](https://www.tensorflow.org/tutorials/images/classification)
- [Binary Image classifier CNN using TensorFlow](https://medium.com/techiepedia/binary-image-classifier-cnn-using-tensorflow-a3f5d6746697) - Sai Balaji
- [10 Minutes to Building a CNN Binary Image Classifier](https://towardsdatascience.com/10-minutes-to-building-a-cnn-binary-image-classifier-in-tensorflow-4e216b2034aa) - Binh Fahn

---

Kylie DeFeo  
Originally created for DSC 344 - Intro to Machine Learning (2022), updated for portfolio presentation.
