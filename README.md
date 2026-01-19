# Blind Source Separation with Neural Networks

This repository contains a deep learning project for **Blind Source Separation (BSS)**, developed as part of a university exam/project.

The goal is to separate two original images from a single input image obtained as the **sum of two sources**, using a **neural network without any preprocessing**.

---

## 📌 Project Description

Given two images:

* one from **MNIST** (handwritten digits)
* one from **Fashion-MNIST** (clothing items)

we generate a mixed image by summing them pixel-wise. The task of the neural network is to **reconstruct the two original images** from the mixed one.

This is a classical **Blind Source Separation** problem, tackled here using a **convolutional neural network** trained end-to-end.

⚠️ **Constraint**: no preprocessing is allowed. The network directly receives the mixed image as input.

---

## 🧠 Approach

* Dataset: `MNIST` + `Fashion-MNIST`
* Input: `x = image_1 + image_2`
* Output: `(image_1_hat, image_2_hat)`
* Loss: **Mean Squared Error (MSE)**
* Framework: **TensorFlow / Keras**

A custom **data generator** is used to dynamically create mixed images during training and testing.

The final model is a **CNN-based encoder–decoder architecture** with:

* Convolutional layers
* Batch Normalization
* Upsampling layers
* Two output branches (one per reconstructed source)

---

## 📂 Repository Structure

```
.
├── blind_source_separation.ipynb   # Main notebook with data loading, model, training and evaluation
├── README.md                       # Project documentation
```

---

## ⚙️ Requirements

* Python ≥ 3.8
* TensorFlow
* NumPy
* Matplotlib

Optional (for model visualization):

* visualkeras

You can install the required dependencies with:

```bash
pip install tensorflow numpy matplotlib visualkeras
```

---

## ▶️ How to Run

1. Clone the repository:

```bash
git clone https://github.com/your-username/blind-source-separation.git
cd blind-source-separation
```

2. Open the notebook:

```bash
jupyter notebook blind_source_separation.ipynb
```

3. Run all cells to:

* load the datasets
* generate mixed images
* train the model
* evaluate reconstruction performance

---

## 📊 Evaluation

Model performance is evaluated using **Mean Squared Error (MSE)** on a test set.

The evaluation is repeated multiple times to obtain a more stable estimate of performance.

Additionally, qualitative results are shown by visualizing:

* mixed input image
* reconstructed MNIST image
* reconstructed Fashion-MNIST image

---

## 🖼️ Results

The final architecture was selected after several experiments, balancing:

* reconstruction quality
* training time
* model complexity

The model is able to reasonably separate the two sources despite the absence of preprocessing and explicit supervision about the mixing process.

---

## 📚 Notes

* This project is intended for **educational purposes**.
* The solution follows the constraints given in the exam specification.
* Further improvements could include deeper architectures, skip connections, or alternative loss functions.

---

## 👤 Author

**Federico Faccioli**
MSc in Artificial Intelligence

---

## 📄 License

This project is released under the **MIT License**. You are free to use, modify, and distribute it for academic and educational purposes.
