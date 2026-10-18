# 🫁 Lung Cancer Detection Using Deep Learning

A deep-learning project that classifies lung tissue images into three categories using a Convolutional Neural Network (CNN) built with TensorFlow/Keras. The project is implemented in a Jupyter Notebook and includes image preprocessing, model training, and evaluation with a confusion matrix and classification report.

> **Important:** This is an educational machine-learning project, not a medical diagnostic tool. Predictions must not be used to make clinical decisions.

## 📌 Overview

This project explores how a CNN can learn visual patterns from labeled lung histopathology images and classify them into the dataset's three classes.

### Classes

| Label | Description |
|---|---|
| `lung_aca` | Lung adenocarcinoma |
| `lung_n` | Normal lung tissue |
| `lung_scc` | Lung squamous cell carcinoma |

The class labels are inherited from the dataset. This prototype has not been validated for clinical use.

## ✨ Features

- Loads and explores labeled lung-tissue images.
- Resizes images to **256 × 256** pixels.
- Splits the data into training and test sets.
- Builds a CNN with convolution, max-pooling, dense, batch-normalization, and dropout layers.
- Trains the model for **10 epochs** using the Adam optimizer.
- Evaluates predictions with a confusion matrix and precision, recall, and F1-score.
- Plots training/validation loss and accuracy.

## 🧰 Tech Stack

- **Python**
- **Jupyter Notebook**
- **TensorFlow / Keras**
- **OpenCV**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Pillow (PIL)**
- **scikit-learn**

## 📁 Repository Structure

```text
Lung-cancer-Detection/
└── Deep learning_project (1).ipynb   # Data preparation, CNN training, evaluation
```

The notebook expects the image dataset to be available locally; the dataset is not included in this repository.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Manikandan1511/Lung-cancer-Detection.git
cd Lung-cancer-Detection
```

### 2. Create and activate a virtual environment (recommended)

**macOS / Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows**
```bash
python -m venv .venv
.venv\\Scripts\\activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install numpy pandas matplotlib pillow opencv-python scikit-learn tensorflow jupyter
```

TensorFlow installation requirements vary by operating system and Python version. If installation fails, consult the official [TensorFlow installation guide](https://www.tensorflow.org/install).

### 4. Prepare the dataset

The notebook expects a directory similar to:

```text
lung_colon_image_set/
└── lung_image_sets/
    ├── lung_aca/
    ├── lung_n/
    └── lung_scc/
```

Each class folder should contain its corresponding JPEG images. Obtain the dataset from its original, authorized source and check its license and terms.

**Important:** Update the `data_path` and `path` variables in the notebook to match your computer. The notebook currently contains a machine-specific path, so it will not run unchanged on every system.

### 5. Run the notebook

```bash
jupyter notebook
```

Open `Deep learning_project (1).ipynb` and execute the cells from top to bottom.

## 🧠 Model Architecture

The notebook defines a sequential CNN with:

1. Convolutional layer with 32 filters and a 5 × 5 kernel.
2. Max-pooling layer.
3. Convolutional layer with 64 filters and a 3 × 3 kernel.
4. Max-pooling layer.
5. Convolutional layer with 128 filters and a 3 × 3 kernel.
6. Max-pooling layer.
7. Flatten layer and a 256-unit dense layer.
8. Batch normalization, a 128-unit dense layer, dropout, and batch normalization.
9. A 3-unit softmax output layer for the three classes.

### Training Configuration

| Parameter | Value |
|---|---|
| Input image size | 256 × 256 × 3 |
| Train/test split | 80% / 20% |
| Batch size | 64 |
| Epochs | 10 |
| Optimizer | Adam |
| Loss function | Categorical cross-entropy |
| Output activation | Softmax |

## 📊 Results

The saved notebook's classification report records these results on its 3,000-image held-out split:

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| `lung_aca` | 0.83 | 0.84 | 0.84 | 987 |
| `lung_n` | 0.99 | 0.94 | 0.96 | 977 |
| `lung_scc` | 0.86 | 0.88 | 0.87 | 1,036 |
| **Overall accuracy** |  |  | **0.89** | **3,000** |
| Macro average | 0.89 | 0.89 | 0.89 | 3,000 |
| Weighted average | 0.89 | 0.89 | 0.89 | 3,000 |

These are the metrics recorded in the existing notebook output; results may vary when retraining or changing the dataset and environment.

### Interpreting the Results

- **Precision** measures how many predictions for a class were correct.
- **Recall** measures how many actual examples of a class were identified.
- **F1-score** balances precision and recall.
- The **confusion matrix** shows correct and incorrect predictions for each class.

The notebook uses the test split as validation data during training and later reports metrics on that same split. For stronger evaluation, use separate training, validation, and final test sets, check for duplicate or related images across splits, and evaluate on independent data. The training curves also vary across epochs, so the reported accuracy should not be interpreted as evidence of clinical reliability.

## 🔭 Possible Improvements

- Replace machine-specific file paths with configurable paths.
- Normalize image pixel values and apply carefully selected data augmentation.
- Use stratified train/validation/test splits and check for data leakage.
- Add early stopping, learning-rate scheduling, and model checkpointing.
- Compare the CNN with transfer-learning models such as MobileNetV2 or EfficientNet.
- Save the trained model and build a reproducible inference script.
- Add per-class metrics, ROC curves where appropriate, and clearer visualizations.
- Test robustness on an independent dataset from a different source.

## ⚠️ Limitations & Responsible Use

- This is an educational prototype trained on a specific labeled image dataset.
- Dataset quality, class balance, image-source differences, and data leakage can affect results.
- The model may perform differently on images from other laboratories, scanners, or populations.
- An accuracy score alone does not establish clinical usefulness or safety.
- **Do not use this project to diagnose, screen, or treat any person.** Medical decisions require qualified clinicians and appropriately validated tools.

## 👨‍💻 Author

**Manikandan**  
GitHub: [@Manikandan1511](https://github.com/Manikandan1511)

## 📄 License

No license file is currently included in this repository. Unless a license is added, all rights remain with the copyright holder. Add an appropriate license before inviting reuse or contributions, and verify the dataset's separate license and terms.

---

⭐ If this project helps your learning, consider starring the repository.
