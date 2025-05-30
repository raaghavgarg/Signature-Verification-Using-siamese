# Signature-Verification-Using-siamese
a real-time signature verification system using a Siamese Convolutional Neural Network (CNN).

This project implements a real-time signature verification system using a **Siamese Convolutional Neural Network (CNN)**. It is trained on the [CEDAR Signature Dataset](http://www.cedar.buffalo.edu/NIJ/data/signatures.zip) to determine whether a given signature is **genuine or forged** by comparing it with a reference signature.



The system uses a Siamese neural network architecture, which consists of two identical CNNs sharing weights. Each CNN processes one of the two input signatures and generates a feature embedding. The Euclidean distance between the two embeddings is then calculated. If the distance is below a certain threshold, the signatures are classified as belonging to the same person (genuine); otherwise, the test signature is flagged as a forgery.

## 📁 Dataset Structure

The model uses the CEDAR dataset, which is organized into two main directories:

* `gen_path/`: Contains folders for each individual, with their **genuine signatures**.
* `forg_path/`: Contains folders with the corresponding **forged signatures** for each individual.

Example structure:

```
CEDAR_dataset/
├── gen_path/
│   ├── person1/
│   └── person2/
└── forg_path/
    ├── person1/
    └── person2/
```

## 🚀 Getting Started

To use this project, first install the required dependencies:

```bash
pip install -r requirements.txt
```

Then, train the Siamese network using:

```bash
python train.py
```

After training, you can test the model by providing two signature images:

```python
from verify import predict_signature

result = predict_signature("original_signature.png", "test_signature.png")
print(result)  # Outputs: 'Genuine Signature' or 'Forged Signature'
```

## ✅ Features

* Real-time signature comparison and verification.
* Siamese CNN architecture for effective similarity learning.
* Works on offline handwritten signatures.
* Easy-to-use interface for training and testing.

## 📌 Roadmap

* [ ] Build a Streamlit-based web interface for live testing.
* [ ] Export the model to ONNX format for broader deployment.
* [ ] Visualize signature embeddings using t-SNE or PCA.



