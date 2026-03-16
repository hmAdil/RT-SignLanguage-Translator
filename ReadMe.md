# SignSens

SignSens is a real-time sign language recognition system built using **PyTorch, OpenCV, and Pygame**.  
The application trains a convolutional neural network on the **Sign Language MNIST dataset** and uses a webcam to recognize hand gestures and translate them into alphabet characters.

The project provides an interactive GUI that allows users to train models and run real-time sign detection.

---

# Features

- Real-time **sign language detection using a webcam**
- **CNN-based image classification model**
- Automatic **dataset downloading from Kaggle**
- Training multiple models and selecting the **best performing model**
- **Interactive GUI built with Pygame**
- GPU acceleration support with **CUDA (if available)**

---

# Project Structure

```
SignSens
│
├── Application.py
├── Camera_Loader.py
├── Dataset_Loader.py
├── Neural_Network_Definition.py
├── Neural_Network_Trainer.py
├── Window_Constants_Definition.py
│
├── Trained_Model.pth
│
└── README.md
```

---

# How It Works

The system works in three major stages:

### 1. Dataset Loading

The dataset is automatically downloaded using KaggleHub and loaded into tensors.

The dataset used is:

Sign Language MNIST

Each image:
- Resolution: **28 x 28**
- Grayscale
- Represents one alphabet sign

---

### 2. Model Training

A **Convolutional Neural Network (CNN)** is trained to classify sign language images.

Architecture overview:

- Convolution Layer (1 → 32)
- ReLU
- Max Pooling
- Convolution Layer (32 → 64)
- ReLU
- Max Pooling
- Convolution Layer (64 → 128)
- ReLU
- Max Pooling
- Fully Connected Layers
- Output Layer (25 classes)

The trainer:

- Trains **multiple models**
- Evaluates each model
- Selects the **highest accuracy model**
- Saves it as

```
Trained_Model.pth
```

---

### 3. Real-Time Sign Detection

Once a trained model exists, the system:

1. Opens the webcam
2. Captures frames continuously
3. Preprocesses each frame
4. Converts it into a tensor
5. Runs inference through the CNN
6. Outputs the predicted alphabet

Press **Q** to exit the camera window.

---

# Installation

Clone the repository:

```
git clone https://github.com/yourusername/signsens.git
cd signsens
```

Install dependencies:

```
pip install torch torchvision
pip install opencv-python
pip install pygame
pip install pandas
pip install kagglehub
pip install matplotlib
```

---

# Running the Application

Run the main application:

```
python Application.py
```

This launches the **SignSens GUI**.

You will see two options:

### Train Model

Trains multiple CNN models and saves the best performing one.

### Translation

Starts the webcam and performs real-time sign detection.

---

# Technologies Used

Programming Language

- Python

Libraries

- PyTorch
- OpenCV
- Pygame
- Pandas
- KaggleHub
- Matplotlib

---

# Model Details

Model Type:

Convolutional Neural Network (CNN)

Input:

```
28 x 28 grayscale image
```

Output:

```
Predicted alphabet character (A–Z excluding one letter depending on dataset)
```

Optimizer:

```
NAdam
```

Loss Function:

```
CrossEntropyLoss
```

---

# Limitations

- Lighting conditions can affect detection accuracy
- Background noise may interfere with gesture recognition
- Model accuracy depends on training quality
- Only supports **static alphabet gestures**

---

# Future Improvements

Possible extensions include:

- Adding **dynamic gesture recognition**
- Using **MediaPipe hand tracking**
- Implementing **Transformer or CNN-LSTM models**
- Supporting **full sign language words**
- Adding **sentence construction**
- Improving UI visualization

---

# Dataset

Sign Language MNIST

Source:

```
https://www.kaggle.com/datamunge/sign-language-mnist
```

The dataset contains labeled images of hand gestures representing alphabet characters.

---

# Author

Developed as a **machine learning and computer vision project** for sign language recognition.

```
Project Name: SignSens
```

---

# License

This project is intended for **educational and research purposes**.
