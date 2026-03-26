 MNIST Digit Recognition   First Neural Network Project

My fourth machine learning project and first deep learning project using neural networks. Built a fully connected neural network with Keras/TensorFlow to recognize handwritten digits from the famous MNIST dataset.

Project Overview

Goal: Classify handwritten digits (0 9) from 28×28 pixel grayscale images

Type: Multi class classification (10 classes)

Dataset: [Kaggle Digit Recognizer Competition](https://www.kaggle.com/c/digit recognizer)
  Training: 42,000 images
  Test: 28,000 images
  Each image: 784 pixels (28×28 grid)
  Pixel values: 0 255 (grayscale intensity)

What Makes This Different from Previous Projects

This is my first neural network project, marking the transition from classical machine learning (Random Forest, Gradient Boosting) to deep learning:

  Input type: Images (pixels) instead of tabular features
  Model type: Neural network instead of tree based models
  Pattern recognition: Spatial relationships between pixels, not individual feature values
  Multi class output: 10 classes (digits 0 9) with probability distribution

Neural Network Architecture
 
Input Layer:     784 neurons (28×28 pixels)
                   ↓
Hidden Layer 1:  128 neurons, ReLU activation
                   ↓
Hidden Layer 2:  64 neurons, ReLU activation
                   ↓
Output Layer:    10 neurons, Softmax activation
                   ↓
Output:          10 probabilities (one per digit)
 

Total Parameters: 109,386 trainable weights

Why this architecture?
  Funnel pattern (784→128→64→10) compresses features
  ReLU adds non linearity for complex pattern learning
  Softmax converts outputs to probabilities that sum to 1

Results

Validation Performance:
  Accuracy: 97.31%
  Training Accuracy: 99.51%
  Gap: ~2% (slight overfitting, acceptable)

Per Digit Performance:
| Digit | Precision | Recall | F1 Score |
|       |           |        |          |
| 0     | 98%       | 99%    | 99%      |
| 1     | 99%       | 99%    | 99%      |
| 2     | 98%       | 95%    | 97%      |
| 3     | 94%       | 98%    | 96%      |
| 4     | 98%       | 96%    | 97%      |
| 5     | 98%       | 95%    | 97%      |
| 6     | 96%       | 99%    | 98%      |
| 7     | 98%       | 97%    | 98%      |
| 8     | 97%       | 97%    | 97%      |
| 9     | 96%       | 97%    | 97%      |

Hardest digits: 3 (confused with 5, 8), 2 and 5 (lower recall)  
Easiest digits: 0, 1, 6 (most distinct shapes)

Technologies Used

  Python 3.x
  TensorFlow/Keras   Neural network framework
  NumPy   Array operations
  Pandas   Data manipulation
  Matplotlib/Seaborn   Visualization
  Scikit learn   Train/test split, metrics

Key Concepts Learned

 Neural Network Fundamentals
  Dense (Fully Connected) Layers: Every neuron connects to every neuron in the next layer
  Activation Functions:
    ReLU (Rectified Linear Unit): `max(0, x)`   adds non linearity
    Softmax: Converts raw scores to probabilities summing to 1
  Forward Propagation: Input → hidden layers → output
  Backpropagation: Adjusting 109,386 weights using gradient descent

 Data Preprocessing for Neural Networks
  Normalization: Scaled pixels from 0 255 to 0 1 for stable learning
  One Hot Encoding: Converted labels (e.g., 3) to vectors (e.g., [0,0,0,1,0,0,0,0,0,0])
  Why? Neural networks need inputs/outputs in specific numerical formats

 Training Mechanics
  Epochs: Number of times the model sees the entire dataset (10 epochs)
  Batch Size: Process 32 images at a time (faster than one by one)
  Optimizer: Adam   smart algorithm for adjusting weights
  Loss Function: Categorical Crossentropy   measures prediction error for multi class
  Learning Rate: 0.001   controls step size during weight updates

 Model Evaluation
  Overfitting Detection: Training accuracy (99.51%) > Validation accuracy (97.31%)
  Confusion Matrix: Shows which digits get confused
  Precision vs Recall: Balance between "correctness when predicting X" vs "finding all X's"

How to Run

1. Clone the repository:
 bash
git clone https://github.com/mabdullah52/mnist digit recognition.git
cd mnist digit recognition
 

2. Open in Kaggle:
  Go to [Digit Recognizer Competition](https://www.kaggle.com/c/digit recognizer)
  Create a new notebook
  Copy the code from this repo

3. Or run locally:
 bash
pip install tensorflow pandas numpy matplotlib seaborn scikit learn
python mnist_digit_recognition.py
 

 📁 Project Structure
 
mnist digit recognition/
│
├── mnist_digit_recognition.ipynb     Main Kaggle notebook
├── submission.csv                    Kaggle submission file
├── README.md                         This file
 

What I Learned

1. Neural networks are fundamentally different from classical ML:
     Not rule based or tree based
     Learn by adjusting millions of parameters
     Excel at finding spatial/sequential patterns

2. Data preprocessing is crucial:
     Normalization stabilizes learning
     One hot encoding matches network output format
     Image data = pixels, not features

3. Architecture design matters:
     Layer sizes affect capacity to learn
     Activation functions add expressiveness
     Output layer design depends on task (Softmax for multi class)

4. Training is an iterative process:
     Model improves over epochs
     Overfitting can happen (memorizing vs learning)
     Validation loss curve shows when to stop

5. Deep learning frameworks (Keras) simplify complexity:
     High level API hides math details
     Focus on architecture, not implementation
     Standard patterns (Sequential, Dense, compile, fit)

Next Steps

Improvements for this project:
  Add dropout layers to reduce overfitting
  Try Convolutional Neural Networks (CNNs) for better spatial learning
  Data augmentation (rotate, shift images) for more training variety
  Early stopping to prevent overfitting automatically

Next project: Moving to CNNs (Convolutional Neural Networks) for better image understanding!

Progress Tracker

|  | Project | Type | Score | Status |
|   |         |      |       |        |
| 1 | Titanic Survival | Classification | 84.36% |  Complete |
| 2 | House Price Prediction | Regression | 0.1486 RMSE |  Complete |
| 3 | Customer Churn | Imbalanced Classification | 79% acc, F1 0.56 |  Complete |
| 4 | MNIST Digit Recognition | Neural Network | 97.31% |  Complete |

Connect

  GitHub: [mabdullah52](https://github.com/mabdullah52)
  LinkedIn: [https://www.linkedin.com/in/abdullah-asim-367889255/]
  Email: abdullahasimnaawaz@gmail.com

   

*Part of my journey from zero to AI/ML engineer. Building projects, learning concepts, and documenting everything along the way.*
 

   

 🎯 Quick Actions

1. Create the README:
  Copy the markdown above
  Save as `README.md` in your project folder
2. Repository Description (use when creating the repo):
 
First deep learning project using neural networks to classify handwritten digits (0 9) from the MNIST dataset. Built with Keras/TensorFlow, achieving 97.31% validation accuracy. Part of my AI/ML learning journey from beginner to advanced.