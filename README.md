# 🐟 Go Fish No Fish: Binary Image Classification with CNN

A Convolutional Neural Network for classifying Caribbean underwater images as containing fish or not containing fish. Built with TensorFlow/Keras.

[![Open In Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://www.kaggle.com/datasets/hiyaro/doesimagehavefish)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 Overview

This project addresses a practical problem in marine biology: efficiently filtering large datasets of underwater images to identify which ones contain fish. The binary classifier achieves **~91% validation accuracy** using a CNN with data augmentation and dropout regularization.

### Key Features
- Custom CNN architecture optimized for binary classification
- Data augmentation pipeline (random flips, rotations, zooms)
- Dropout regularization to prevent overfitting
- Comprehensive evaluation with confusion matrix and classification report
- Clean, well-documented code ready for production

## 🎯 Problem Statement

Marine biologists often work with thousands of underwater images for fish identification and counting. Many images don't contain fish at all. This classifier automatically filters images into "contains fish" and "no fish" categories, allowing researchers to focus their time on relevant images.

## 📊 Results

| Metric | Score |
|--------|-------|
| Validation Accuracy | ~91% |
| Training Accuracy | ~93% |
| Model Parameters | ~1.2M |

The model shows minimal overfitting, with training and validation curves closely aligned.

## 🛠️ Tech Stack

- **Python 3.8+**
- **TensorFlow/Keras** - Deep learning framework
- **NumPy** - Numerical computing
- **Matplotlib/Seaborn** - Visualization
- **scikit-learn** - Evaluation metrics

## 📁 Project Structure

```
gofishnofish/
├── gofishnofish.ipynb       # Main notebook with full pipeline
├── README.md                # This file
├── requirements.txt         # Python dependencies
├── .gitignore              # Git ignore rules
└── LICENSE                 # MIT License
```

## 🚀 Quick Start

### Option 1: Run on Kaggle (Recommended)
1. Go to the [Blue Bot Dataset](https://www.kaggle.com/datasets/hiyaro/doesimagehavefish) on Kaggle
2. Click "New Notebook"
3. Upload or copy the code from `fish_classifier.ipynb`
4. Run all cells

### Option 2: Run Locally

```bash
# Clone the repository
git clone https://github.com/kdefeo5/gofishnofish.git
cd gofishnofish

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download the dataset from Kaggle
# (Requires Kaggle API credentials)
kaggle datasets download -d hiyaro/doesimagehavefish
unzip doesimagehavefish.zip -d data/

# Run the notebook
jupyter notebook gofishnofish.ipynb
```

## 🏗️ Model Architecture

```
Input (150x150x3)
    ↓
Data Augmentation (RandomFlip, RandomRotation, RandomZoom)
    ↓
Rescaling (1/255)
    ↓
Conv2D (16 filters, 3x3) + ReLU → MaxPool
    ↓
Conv2D (32 filters, 3x3) + ReLU → MaxPool
    ↓
Conv2D (64 filters, 3x3) + ReLU → MaxPool
    ↓
Dropout (0.2)
    ↓
Flatten → Dense (128, ReLU) → Dense (2)
    ↓
Output (Fish / No Fish)
```

## 📈 Training Details

- **Optimizer:** Adam
- **Loss:** Sparse Categorical Crossentropy
- **Epochs:** 15
- **Batch Size:** 32
- **Image Size:** 150x150 pixels
- **Validation Split:** 20%

## 🔮 Future Improvements

- [ ] Transfer learning with ResNet50 or EfficientNet
- [ ] Learning rate scheduling
- [ ] Hyperparameter tuning with Keras Tuner
- [ ] Model deployment as REST API
- [ ] Multi-class fish species classification

## 📚 References

- [TensorFlow Image Classification Tutorial](https://www.tensorflow.org/tutorials/images/classification)
- [Blue Bot Dataset on Kaggle](https://www.kaggle.com/datasets/hiyaro/doesimagehavefish)
- Brownlee, J. (2019). "How to Develop a CNN From Scratch for CIFAR-10 Photo Classification"

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Kylie DeFeo**
- MSc Artificial Intelligence & Ethics, Northeastern University London
- [GitHub](https://github.com/kdefeo5)

---

*Go Fish No Fish was originally developed as part of DSC 344 - Intro to Machine Learning, updated for portfolio presentation.*
