# StyleGAN on CIFAR-10 using TensorFlow

## 📌 Project Overview

This project implements a simplified StyleGAN-inspired Generative Adversarial Network (GAN) using TensorFlow and Keras to generate synthetic images similar to images in the CIFAR-10 dataset.

The model consists of a **Generator** and a **Discriminator** that compete during training. The Generator learns to produce realistic-looking images, while the Discriminator learns to distinguish real images from generated ones.

The project also demonstrates style mixing and latent space interpolation to explore how different latent vectors influence generated images.

## 🎯 Objectives

- Implement a StyleGAN-inspired architecture using TensorFlow and Keras.
- Generate synthetic images at a resolution of 32 × 32 pixels.
- Train the Generator and Discriminator using adversarial learning.
- Visualize generated images and training loss curves.
- Demonstrate style mixing at different synthesis layers.
- Explore latent space interpolation between two random vectors.

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- CIFAR-10 Dataset
- Jupyter Notebook

## 📂 Dataset

The project uses the CIFAR-10 dataset, which contains 60,000 color images of size 32 × 32 pixels across 10 classes.

The classes include:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

In this implementation, the first **20,000 training images** are used to keep training manageable. The images are normalized to the range [-1, 1].

## 🧠 Model Architecture

### 1. Mapping Network
- Accepts a random latent vector of dimension 128.
- Uses eight fully connected layers.
- Transforms the input latent vector into a style representation.

### 2. Generator
- Uses a learned constant as the initial feature map.
- Applies styled convolutional layers and Adaptive Instance Normalization (AdaIN).
- Progressively increases the feature map resolution from 4 × 4 to 32 × 32.
- Generates RGB images using a final convolutional layer with a `tanh` activation.

### 3. Discriminator
- Uses convolutional layers to analyze input images.
- Extracts image features while reducing spatial resolution.
- Produces a score used to distinguish real images from generated images.

### 4. Training Process
- Trains the Generator and Discriminator using adversarial loss functions.
- Uses the Adam optimizer with a learning rate of 0.0002.
- Runs for 10 epochs with a batch size of 64.
- Records Generator and Discriminator losses for visualization.

## ✨ Key Features

- **Image Generation:** Generates synthetic 32 × 32 RGB images.
- **Adversarial Training:** Trains the Generator and Discriminator together.
- **Loss Visualization:** Plots Generator and Discriminator losses across epochs.
- **Style Mixing:** Combines styles from two latent vectors at different synthesis layers.
- **Latent Space Interpolation:** Generates a sequence of images between two latent vectors.
- **Reproducibility:** Uses a fixed random seed for more consistent initialization and sampling.

## 📋 Requirements

Install the required Python libraries:

```bash
pip install tensorflow numpy matplotlib jupyter
```

Python and TensorFlow versions should be compatible with your operating system and hardware.

## 🚀 How to Run the Project

1. Clone or download this repository.
2. Open a terminal in the project directory.
3. Install the required dependencies.
4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `StyleGAN_CIFAR10_TensorFlow.ipynb`.
6. Run the notebook cells sequentially.
7. Allow the model to train and inspect the generated images, loss plots, style mixing, and interpolation results.

The CIFAR-10 dataset is downloaded through the Keras dataset API when the corresponding cell is executed. An internet connection may be required for the initial download.

## 📊 Expected Outputs

After running the notebook, you should see:

- Sample real images from CIFAR-10.
- Generator and Discriminator training loss values.
- A graph showing the loss curves.
- A grid of generated synthetic images.
- Visual examples of style mixing.
- A sequence of images showing latent space interpolation.

**Note:** Image quality depends on training duration, model configuration, and available computational resources. Ten epochs may not be sufficient to produce high-quality or class-specific images.

## 📁 Project Structure

```text
StyleGAN-CIFAR10-TensorFlow/
│
├── StyleGAN_CIFAR10_TensorFlow.ipynb
└── README.md
```

## 🔮 Future Enhancements

- Train the model for more epochs.
- Improve image quality and training stability.
- Implement progressive training at multiple resolutions.
- Add checkpoint saving and model loading.
- Evaluate generated images using suitable generative-model metrics.
- Experiment with different latent dimensions and network configurations.
- Extend the model to larger image datasets.

## ⚠️ Limit
