# Adaptive Noise Cancellation using LMS and MLP Neural Networks

An AI/ML-based project that explores adaptive noise cancellation by combining traditional signal processing algorithms with machine learning techniques. The project compares multiple learning algorithms to understand their effectiveness in removing linear and nonlinear noise from audio signals.

## 📌 Project Overview

Adaptive Noise Cancellation (ANC) is a technique used to reduce unwanted background noise from audio signals while preserving the original desired signal.

This project implements an adaptive noise cancellation system using the **Least Mean Squares (LMS)** algorithm and compares its performance with other learning approaches, including Normalized LMS (NLMS), Recursive Least Squares (RLS), Linear Regression, and Multi-Layer Perceptron (MLP) Neural Networks.

The system generates noisy audio signals by combining clean audio with artificially generated noise and evaluates how effectively different algorithms can estimate and remove the unwanted noise.

A key focus is understanding how traditional adaptive filtering techniques perform compared to neural networks, particularly when dealing with nonlinear noise.

## 🎯 Objectives

- Understand adaptive noise cancellation using gradient descent.
- Implement the LMS algorithm as a single-neuron learning model.
- Compare LMS with NLMS, RLS, Linear Regression, and MLP Neural Networks.
- Evaluate model performance under linear and nonlinear noise conditions.
- Study the effect of learning rate and filter length on model performance.
- Visualize model convergence, weight adaptation, and noise reduction.
- Develop an interactive noise cancellation demonstration using Gradio.

## ⚙️ Algorithms Implemented

| Algorithm | Description |
|---|---|
| LMS | Adaptive filtering using gradient descent with sample-by-sample weight updates. |
| NLMS | Normalized LMS with an adaptive step size based on input signal power. |
| RLS | Recursive Least Squares algorithm that uses previous information to update filter weights. |
| Linear Regression | Estimates optimal linear filter weights using a direct mathematical approach. |
| MLP Neural Network | A multi-layer perceptron capable of learning nonlinear relationships in noisy audio signals. |

## 🧠 Methodology

The project follows these major stages:

### 1. Audio Input and Preprocessing
- Upload a clean audio recording containing music or speech.
- Convert the audio into mono format.
- Resample the audio to 8,000 Hz.
- Normalize the audio signal for consistent processing.

### 2. Noise Generation

Two types of noise scenarios are created:

- **Linear Noise:** Noise passes through a simulated room response represented by a set of filter coefficients.
- **Nonlinear Noise:** Noise undergoes nonlinear distortion using clipping and squaring operations to simulate more complex noise conditions.

An input Signal-to-Noise Ratio (SNR) of 5 dB is used by default.

### 3. Feature Extraction

A reference noise signal is converted into a delayed sample matrix.

Each row contains the current reference sample and previous samples, which serve as input features for the learning algorithms.

### 4. Model Training and Testing

The generated audio is divided into:
- Training data: First 40% of the audio.
- Testing data: Remaining 60% of the audio.

All implemented algorithms learn from the training portion and are evaluated on unseen test audio.

### 5. Performance Evaluation

The algorithms are compared using:
- Output Signal-to-Noise Ratio (SNR).
- SNR improvement in decibels.
- Noise reduction effectiveness.
- Learning convergence and stability.

### 6. Visualization and Analysis

The notebook generates:
- Comparative bar charts for different algorithms.
- Clean, noisy, and filtered audio waveform comparisons.
- LMS weight convergence plots.
- Neural network training loss plots.
- Learning rate and filter length analysis.

### 7. Audio Output

The processed audio signals can be played directly in Google Colab and saved as WAV files for further comparison.

## 📐 Mathematical Concepts

This project demonstrates the application of mathematical optimization and gradient descent in adaptive filtering.

**1. Least Mean Squares (LMS)**

The LMS algorithm updates filter weights iteratively to minimize the prediction error.

Weight update equation:

w(n+1) = w(n) + μe(n)x(n)

Where:
- w(n) = Current filter weights
- μ = Learning rate
- e(n) = Prediction error
- x(n) = Input reference vector

**2. Signal-to-Noise Ratio (SNR)**

SNR measures the strength of the desired signal relative to the remaining noise.

SNR (dB) = 10 log₁₀(P_signal / P_noise)

A higher SNR indicates better noise cancellation.

**3. Learning Rate Optimization**

The learning rate determines how quickly the LMS algorithm updates its weights. Different learning rates are tested to observe convergence, stability, and performance.

**4. Filter Length Optimization**

Different filter lengths (number of delayed reference samples) are evaluated to understand their influence on noise estimation and cancellation performance.

## 🛠️ Technologies Used

- Python
- Google Colab
- NumPy
- Pandas
- Matplotlib
- Librosa
- SoundFile
- Scikit-learn
- Gradio

## 🚀 Running the Project

The project is implemented in Google Colab.

1. Open the notebook in Google Colab.
2. Install the required dependencies.
3. Upload a clean audio file (WAV or MP3).
4. Execute the notebook cells sequentially.
5. Observe the algorithm comparison tables and visualizations.
6. Listen to the original, noisy, and filtered audio outputs.
7. Explore the interactive Gradio interface to test different algorithms and noise conditions.

## 🎧 Interactive Demonstration

The project includes a Gradio-based interface that allows users to:

- Upload clean audio recordings.
- Optionally upload a real noise recording.
- Select linear or nonlinear noise conditions.
- Choose an adaptive filtering or machine learning algorithm.
- Adjust the learning rate.
- Control the input SNR.
- Listen to noisy and cleaned audio outputs.
- Compare SNR before and after noise cancellation.

## 📊 Key Highlights

- Comparative analysis of five noise cancellation approaches.
- Evaluation under both linear and nonlinear noise conditions.
- LMS implemented as a gradient-descent-based single-neuron model.
- Neural network implementation using an MLP architecture with hidden layers of 64 and 32 neurons.
- Analysis of learning rate and filter length.
- Performance evaluation using unseen test audio.
- Interactive audio processing through Gradio.

## 🔮 Future Scope

- Implement real-time noise cancellation using microphone input.
- Explore advanced deep learning architectures for audio enhancement.
- Test the system with larger real-world noise datasets.
- Optimize the models for embedded and edge devices.
- Improve performance under dynamic environmental noise conditions.

## 👥 Project Information

**Project:** Adaptive Noise Cancellation using LMS and MLP Neural Networks

**Category:** Artificial Intelligence and Machine Learning

**Platform:** Google Colab

**Application:** Digital Signal Processing and Machine Learning

## 📓 Google Colab Notebook

Explore the complete implementation, model training, algorithm comparisons, and visualizations in the Google Colab notebook.

**[🚀 Open Project Notebook in Google Colab](https://colab.research.google.com/drive/1tYh7oqLgZHvtd2p3cWelL714uIUt7Jd5)**

---


*This project demonstrates how adaptive filtering, gradient descent, and neural networks can be applied to audio noise cancellation, while highlighting the strengths and limitations of different learning algorithms.*
